###### Java



## Java 8 Stream API



###### Java EE

## JAX-RS

## JDBC

## OpenJPA

## Hibernate

## EJB

## CDI

## JSP

## Servlets APIs

###### Spring

## Framework 4/5

## Design Patterns

## Boot

@EnableAutoConfiguration
@AutoConfigureBefore
@AutoConfigureAfter

> Conditional Loading:
@ConditionalOnClass
@ConditionalOnBean
@ConditionalOnProperty
@ConditionalOnMissingBean
@ConditionalOnMissingClass
application type based
resource (or file) based
expression based

> Properties:
@EnableConfigurationProperties

> Property-based configurations
- application.properties or application.yml
- environment properties
- command-line injections
- cloud configurations (config server, vault, consul) - most common for Spring Boot Cloud Native)

> Bean configurations
- adding beans to the default application class
- adding beans to separate configuration classes
- importing XML-based configurations
- component scanning

> Profiles
application.yml: different properties, run by specify -D property in cmd when java run jar

spring:
	profiles: dev
---
spring:
	profiles: prod

Real world examples:
- Third-party dependencies
- LogLevel changes (f.e. DEBUG on Test environment and WARN on prod)
- Service deployments
- internal resource deployments

> spring-boot-starter-web artifact dependency
- no difference between HTML-based web apps and web services (you can use both), both leverage spring-boot-starter-web
- mixture of components needed to get apps going
- default embedded Tomcat server, can be replaced with Undertow or Jetty
- you can remove Tomcat completely to create war
- with Spring Web you get Jackson JSON marshaller, useful for RESTful web services
- logging: slf4j included, Spring Boot builds its own loggers, leverage properties to modify LogLevels, variation of Logback and JBoss logging if you choose
- Spring libraries: Spring Boot Auto configure; Spring Boot starters for Tomcat, logging and Boot; Spring Core; AOP (aspects); beans; context; expression;
Spring web and webmvc; SnakeYAML, Validators (javax and Hibernate)

> Configuring embedded Tomcat
Servlets, Filters and Listeners:
- Spring Boot autoconfigures the default servlet for all responses at "/"
- any class of these types that are beans (config or component scanned) will be registered to the embedded container
- Additional ServletContext can only be loaded through the ServletContextInitializer interface

Property-based configuration:
- application.properties or yml: server.address, server.port, server.contextPath
- Session-based configs (cookies, timeouts etc.)
- Error pages paths
- See class for full list:
org.springframework.boot.autoconfigure.web.ServerProperties

Compression:
- server.compression.enabled=true
- response must be 2048 bytest to compress by default
- default Response Types of text/html, text/xml, text/plain, text/css (MIME types) will be compressed by default

TLS/SSL:
- native SSL support via property management
- most common embedded servlet change
- requires a Java Keystore that contains the certificate
keytool -genkey -keyalg RSA -alias alias -keystore keystore.jks -storepass password -validity 4000 -keysize 4096
application.yml:	
server:	
	ssl: 
		key-store: classpath:keystore.jks
		key-store-password: password
		key-store-type: JKS
		key-alias: alias
		key-password: password
		
or use Keycloak or other cloud-based solution (Key Vault in Azure)
- properties used to configure


## MVC

## Data

## Cloud

## Security



###### DB

## Left Join

## Right Join

## Group By

## Partitions


######
