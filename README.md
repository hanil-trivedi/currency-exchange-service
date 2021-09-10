# currency-exchange-service
part of Currency Application currency-exchange-service   ,  currency-conversion-service , git-localconfig-repo and spring-cloud-config-server

1.Setting up Currency Exchange Microservice On Spring Initializr, choose: Group Id: com.hanil.microservices
  , Artifact Id: currency-exchange-service ,
  
2.Dependencies - Web,DevTools , Actuator,Config Client

3.Create a simple hard coded currency exchange service - http://localhost:8000/currency-exchange/from/USD/to/INR ,

4.Setting up Dynamic Port in the the Response,VM Arguments : -Dserver.port=8001 to launch on 8001 , Adding private 
5.String environment and getters and setters,

6.Configure JPA and Initialized Data , If you are Spring Boot >=2.5.0, You would need to configure this in   application.properties -spring.jpa.defer-datasource-initialization=true 
  OR use schema.sql instead of data.sql

7.Create a JPA Repository and then call from controller instead of hardcoded values.and the url will be http://localhost:8000/currency-exchange/from/USD/to/INR


* Step 20 - Connect Currency Conversion Microservice & Currency Exchange Microservice to Eureka

/currency-exchange-service/pom.xml Modified
New Lines

		<dependency>
			<groupId>org.springframework.cloud</groupId>
			<artifactId>spring-cloud-starter-netflix-eureka-client</artifactId>
		</dependency>
/currency-exchange-service/src/main/resources/application.properties Modified
New Lines

eureka.client.serviceUrl.defaultZone=http://localhost:8761/eureka