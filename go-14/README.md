# Go 14

Jenkins X build image extending the Jenkins X base image, for building Go lang apps with Go 1.14.

The default Go builder image uses Go 1.12, so if you need a newer version, feel free to use this one.

## Usage

```yaml
buildPack: go
pipelineConfig:
  agent:
    image: caladreas/jx-builder-go14:v0.7.0 
```