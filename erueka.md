# 项目部署

## erueka的创建

（1）pom.xml依赖

创建模块changgou_eureka，pom.xml引入依赖 

```xml
<dependencies>
    <dependency>
        <groupId>org.springframework.cloud</groupId>
        <artifactId>
          spring-cloud-starter-netflix-eureka-server
      </artifactId>
    </dependency>
</dependencies>
```

（2） appliation.yml配置

创建配置文件application.yml

```yml
server:
  port: 6868
eureka:
  client:
    register-with-eureka: false #是否将自己注册到eureka中
    fetch-registry: false #是否从eureka中获取信息
    service-url:
      defaultZone: http://127.0.0.1:${server.port}/eureka/
```

（3）启动类配置

创建包com.changgou.eureka  包下创建启动类

```java
@SpringBootApplication  //启动类
@EnableEurekaServer  //启动erueka
public class EurekaApplication {
    public static void main(String[] args) {
        SpringApplication.run(EurekaApplication.class);
    }
}
```

