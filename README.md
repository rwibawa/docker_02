# HelloWorld docker image

## 1. Docker commands
```bash
  $ docker run alpine:latest "echo" "Hello, world"
  $ docker images

  $ vi HelloWorld.java
  $ javac HelloWorld.java
  $ java HelloWorld
  $ vi Dockerfile

  $ docker build --tag "docker-hello-world:latest" .
  $ docker run docker-hello-world:latest

  $ docker ps -a
  $ docker stop e7759fdbbbe2
  $ docker rm dfd59bdedb1e
```

## 2. HelloWorld.java
```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World");
    }
}
```

## 3. Dockerfile
```docker
FROM alpine:latest
ADD HelloWorld.class HelloWorld.class
RUN apk --update add openjdk8-jre
ENTRYPOINT ["java", "-Djava.security.egd=file:/dev/./urandom", "HelloWorld"]
```
