# Introduction
This is a minimal Spring Boot application which is used for
demo purposes.

# Demo Video

[![](https://i.imgur.com/1yfhFr8.jpg)](./assets/demo.mp4)

# Usage

This app uses Sprinboot profiles which allows the application
reads different properties file from the following files based on
the active environment
* application.properties (all env)
* application.dev-properties (spring_profile_active=dev)
* application.uat-properties (spring_profile_active=uat)
* application.prod-properties (spring_profile_active=prod)

The active environment can be switched using `export spring_profile_active=ENV`
environment variable.

```
git clone https://github.com/jarviscanada/jarvis_springboot_demo_app.git 
cd jarvis_springboot_demo_app
mvn clean package

#Run the app
export spring_profiles_active=dev
java -jar target/SpringbootDemoApp-1.0.1-SNAPSHOT.jar

#Print greeting message
curl localhost:8082/

#Print all java properties (using Springboot actuator module)
curl localhost:8082/actuator/env
```

# Springboot Actuator

Actuator English definition:
> An actuator is a manufacturing term that refers to a mechanical device for moving or controlling something. Actuators can generate a large amount of motion from a small change.

Springboot Actuator:
> Spring Boot includes several additional features to help you monitor and manage your application when you push it to production. You can choose to manage and monitor your application by using HTTP endpoints or with JMX. Auditing, health, and metrics gathering can also be automatically applied to your application.
  
[Actuator doc](https://docs.spring.io/spring-boot/docs/current/reference/htmlsingle/#production-ready)

Try common endpoints using the demo app:
* localhost:8082/actuator/env
* localhost:8082/actuator/health
* localhost:8082/actuator/beans