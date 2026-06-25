# stackgres

Get `admin` passowrd:
```bash
kubectl -n stackgres \
  get secret stackgres-restapi-admin \
  --template='{{printf "username: %s\npassword: %s\n" (index .data "k8sUsername" | base64decode) (index .data "clearPassword" | base64decode)}}' 2>&1
```
