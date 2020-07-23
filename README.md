# dingtalk-alertmanager-konvoy

## Step 1 -- request dingtalk chatbot credential

[Ding chatbot request guide](https://blog.csdn.net/knight_zhou/article/details/105583741)

## Step 2 -- deploy dingtalk altermanager webhook proxy

```
kubectl apply -f dingtalk-webhook.yaml
```

## Step 3 -- run below kubectl command

```
kubectl create secret generic -n kubeaddons \
  alertmanager-prometheus-kubeaddons-prom-alertmanager \
  --from-file=alertmanager.yaml \
  --from-file=notification.tmpl \
  --dry-run=client --save-config -o yaml | kubectl apply -f -
```
