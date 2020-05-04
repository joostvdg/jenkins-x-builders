# Graal VM Maven JDK 11

Jenkins X build image extending the Jenkins X base image, for building JDK 11 apps with Maven and Graal VM.

Designed to work with [Quarkus' Native Image Build](https://quarkus.io/guides/building-native-image), for building native images with [Graal VM](https://www.graalvm.org/docs/reference-manual/native-image/).

* Maven 3.6+
* OpenJDK 11
* Graal VM 20.20

## Usage

```yaml
buildPack:  maven-java11
pipelineConfig:
  agent:
    image: caladreas/jx-builder-graalvm-maven-jdk11:v0.7.0
```