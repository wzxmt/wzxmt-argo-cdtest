# deployer-deltademo

1、创建名称空间

```bash
kubectl create ns delta
```

2、创建docker-registry

```
cat << EOF >registry-secret.yaml
apiVersion: v1
kind: Secret
metadata:
  namespace: delta
  name: harborlogin
type: kubernetes.io/dockerconfigjson
data:
  .dockerconfigjson: $(cat $HOME/.docker/config.json |base64 -w 0)
EOF
kubectl create -f registry-secret.yaml
```

3、部署服务

```
kubectl apply -f ./
```

# argo-cdtest
# argo-cdtest
# argo-cdtest
