# Java Dockerfiles

This Dockerfile builds an image based on the `amazoncorretto:19-alpine-jdk` image from [Docker Hub](https://hub.docker.com). When you start the container, Docker copies the contents of your project's output directory (in this case, the main class `HelloWorld.class` from `./out`) to the `/tmp` directory in the container. Then Docker runs the java `HelloWorld` command from inside the `/tmp` directory. As a result, you should see `Hello, World!` printed to the container log.

## Build

Use Java to build the `HelloWorld.class` file in the `./out` directory:

```console
C:\Users\antonio> javac -d ./out HelloWorld.java
```

Then, build the image:

```console
C:\Users\Nacho\OneDrive - UNIVERSIDAD DE SEVILLA\MASTER\15 LABORATORIO> docker build -t docker-hello-java .
```

## Run

Run the following command to start the container:

```console
C:\Users\Nacho\OneDrive - UNIVERSIDAD DE SEVILLA\MASTER\15 LABORATORIO> docker run docker-hello-java
Hello World
```