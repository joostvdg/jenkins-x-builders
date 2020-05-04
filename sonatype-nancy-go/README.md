# Sonatype Nancy Go

Jenkins X build image extending the Jenkins X base image, for testing Go lang apps with [Sonatype's Nancy](https://github.com/sonatype-nexus-community/nancy) and [OSS Index](https://ossindex.sonatype.org/).

## Usage

### Create Secret

```sh
kubectl create secret generic -n jx sonatype-oss-index \
  --from-literal=OSS_INDEX_USER='<Sonatype OSS Index User>'\
  --from-literal=OSS_INDEX_TOKEN='<Sonatype OSS Index API Token>'
```

```yaml
buildPack: go
pipelineConfig:
  agent:
    image: caladreas/jx-builder-nancy-go:v0.8.0
  pipelines:
    overrides:
      - name: container-build
        stage: build
        containerOptions:
          envFrom:
            - secretRef:
                name: sonatype-oss-index
        step:
          name: sonatype-nancy
          command: go list -m all | nancy -user $OSS_INDEX_USER -token $OSS_INDEX_TOKEN
        type: before
```