# dingtalk-alertmanager-konvoy

## Step 1 -- request dingtalk chatbot credential

## Step 2 -- deploy dingtalk altermanager webhook proxy

## Step 3 -- run below kubectl command

```
kubectl create secret generic -n kubeaddons \
  alertmanager-prometheus-kubeaddons-prom-alertmanager \
  --from-file=alertmanager.yaml \
  --from-file=notification.tmpl \
  --dry-run=client --save-config -o yaml | kubectl apply -f -
```
