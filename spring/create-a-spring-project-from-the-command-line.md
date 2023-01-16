# Create A Spring Project From The Command Line

__Category: Spring__

You can create a Spring project from the command line using `curl`. 

This example is for Spring Boot with two dependencies: `web` and `security`.

```shell
curl https://start.spring.io/starter.zip \
  -d dependencies=web,security \
  -d type=gradle-project \
  -d bootVersion=3.0.0 \
  -d groupId=com.orbiks.manuka \
  -d artifactId=application \
  -o ManukaProject.zip
```

Unzip the project to a directory caled `manuka`:

```shell
unzip ManukaProject.zip -d manuka
```
