# spring-boot-starter-dubbox 用于集成spring-boot项目

采用dubbox2.8.4版本，由于当当没有将dubbox2.8.4发布到maven中央仓库，大家需要自己去编译到本地仓库才可以使用。

本项目也需要大家自己下载源码进行编译即可。
```
<!-- dubbox -->
<dependency>
	<groupId>com.cxytiandi</groupId>
	<artifactId>spring-boot-starter-dubbox</artifactId>
        <version>1.0.0</version>
</dependency>

 ```

使用也很简单,可以结合[Smconf](https://github.com/yinjihuan/smconf)使用
```
spring.dubbo.scan=com.cxytiandi.ld.service.rpc
spring.dubbo.application.name=${spring.dubbo.applicationName}
spring.dubbo.registry.address=${spring.dubbo.registryAddress}
spring.dubbo.protocol.name=${spring.dubbo.protocolName}
spring.dubbo.protocol.port=${spring.dubbo.protocolPort}
spring.dubbo.protocol.serialization=kryo
```
上面只是一些常用的配置，其余的配置可以参考配置类,前缀是spring.dubbo
https://github.com/yinjihuan/dubbo/blob/master/spring-boot-starter-dubbox/src/main/java/com/cxytiandi/dubbo/DubboProperties.java

上面只是用属性文件的配置方式代替了xml的方式，至于怎么发布和调用服务，也用注解代替了xml
```
@Component("LdRpcService")
@Service(interfaceClass = LdRpcService.class, version = Constants.V1, timeout = 1000)
public class LdRpcServiceImpl implements LdRpcService {
	
	@Reference(interfaceClass = HouseRpcService.class, version = Constants.V1, check = false)
	private HouseRpcService houseRpcService;
	
}
```
# 作者
- 尹吉欢 1304489315@qq.com
- 博客 http://cxytiandi.com/blogs/yinjihuan
