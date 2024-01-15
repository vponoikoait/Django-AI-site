# Prerequisites
## Create secret for application
```bash
touch secret.yaml
```
```yaml 
# secrets.yaml
apiVersion: v1
kind: Secret
metadata:
  name: chatty-env
type: Opaque
data:
  API_KEY: base64_encoded_value
  SECRET_KEY: base64_encoded_value
  DATABASE_NAME: base64_encoded_value
  DATABASE_USER: base64_encoded_value
  DATABASE_PASSWORD: base64_encoded_value
  DATABASE_HOST: base64_encoded_value
  DATABASE_PORT: base64_encoded_value
```
```bash
kubectl apply -f secret.yaml -n django-ai-site
```
# Helm chart 
## Install 
```bash
helm install django-ai-site-release chart/ --namespace django-ai-site --create-namespace -f chart/values-example.yaml
```
## Upgrade
```bash
helm upgrade django-ai-site-release chart/ --namespace django-ai-site -f chart/values-example.yaml
```