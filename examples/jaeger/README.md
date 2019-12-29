# Jaeger Example

This is a simple example that demonstrates how to use the OpenTelemetry SDK 
to instrument a simple application using Jaeger as trace exporter. 

# How to run

## Prerequisites
* Java 1.8.231
* Docker 19.03
* Jaeger 1.16 - [Link][jaeger]


## 1 - Compile 
```bash
gradlew fatJar
```
## 2 - Run Jaeger

```bash
docker run --rm -it --name jaeger\
  -p 16686:16686 \
  -p 14250:14250 \
  jaegertracing/all-in-one:1.16
```


## 3 - Start the Application
```bash
java -cp build/libs/opentelemetry-example-jaeger-all-0.2.0.jar io.opentelemetry.example.Main localhost 14250
```
## 4 - Open the Jaeger UI

Navigate to http://localhost:16686

[jaeger]:[https://www.jaegertracing.io/docs/1.16/getting-started/
