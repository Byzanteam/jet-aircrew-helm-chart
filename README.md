# Jet Aircrew App

## Installation

### make `values.local.yaml`
1. set imageCredentials for image pulling
```yaml
# values.local.yaml
imageCredentials:
  registry: registry.cn-hangzhou.aliyuncs.com
  username: deploy-man@skylark
  password: changeit
```

2. set image info for image pulling
```yaml
# values.local.yaml

image:
  repository: jet/aircrew
  tag: "latest"
  pullPolicy: IfNotPresent
```

3. set host and environments for aircrew
```yaml
# values.local.yaml

# Application
aircrewHost: aircrew.jet.localhost

# Frontend environments
subpath: /
baseUrl: /
jetEndpoint: https://jet.work
appAssetsEndpoint: https://oss.jet.work/minio-public
enableHomepage: false
applicationName: Jet Aircrew

# ICP 备案文案
ICPRecord: ""
# ICP 备案指向链接
ICPRecordLink:  ""
# 公安部备案文案
cyberSecurityRecord: ""
# 公安部备案指向链接
cyberSecurityRecordLink: ""

localeDomain: default
```

### make install
```bash
# set release-name in `.env` file

# .env
RELEASE=aircrew

make install
```

```bash
# set release-name
make install RELEASE=gxzh
```

## HowTo

### Setup TLS
```yaml
# values.local.yaml

aircrewTLSSecret:
  certificate: base64 encoded certificate-file
  key: base64 encoded key-file
```

### Setup Sentry
```yaml
# values.local.yaml

sentryDsn: "sentry-dsn"
sentryRelease: "unique-release-name"
```
