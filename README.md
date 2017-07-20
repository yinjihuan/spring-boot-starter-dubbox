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

使用也很简单,可以结合Smconf使用
```
spring.dubbo.scan=com.cxytiandi.ld.service.rpc
spring.dubbo.application.name=${spring.dubbo.applicationName}
spring.dubbo.registry.address=${spring.dubbo.registryAddress}
spring.dubbo.protocol.name=${spring.dubbo.protocolName}
spring.dubbo.protocol.port=${spring.dubbo.protocolPort}
spring.dubbo.protocol.serialization=kryo
```
