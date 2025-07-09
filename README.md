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

```
oc describe bc hello-world
Webhook GitHub:
	URL: https://api.demo-6.ps-redis.com:6443/apis/build.openshift.io/v1/namespaces/default/buildconfigs/hello-world/webhooks/<secret>/github
## get <secret>
oc get bc hello-world -o jsonpath='{.spec.triggers[?(@.type=="GitHub")].github.secret}'
```
```
Go to your GitHub repo → Settings → Webhooks

Click Add webhook

Fill in the following:

Field	Value
Payload URL	https://api.demo-6.ps-redis.com:6443/apis/build.openshift.io/v1/namespaces/default/buildconfigs/hello-world/webhooks/abc123/github
Content type	application/json
Secret	Leave blank (or use abc123 if needed for validation)
Events	Select “Just the push event”
```
