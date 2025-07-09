# openshift-build

```
oc new-build --name=hello-world \
  --strategy=docker \
  --context-dir=hello-world-docker \
  https://github.com/reza-rahim/openshift-build.git
```

```
oc start-build hello-world

```
