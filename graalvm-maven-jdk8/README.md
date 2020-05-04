# Graal VM Maven JDK 8

Jenkins X build image extending the Jenkins X base image, for building JDK 8 apps with Maven and Graal VM.

Designed to work with [Quarkus' Native Image Build](https://quarkus.io/guides/building-native-image), for building native images with [Graal VM](https://www.graalvm.org/docs/reference-manual/native-image/).

* Maven 3.6+
* OpenJDK 8
* Graal VM 20.20

## Usage

```yaml
buildPack:  maven-java
pipelineConfig:
  agent:
    image: caladreas/jx-builder-graalvm-maven-jdk8:v0.7.0
```