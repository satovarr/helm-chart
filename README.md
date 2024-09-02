```bash
make the changes in chart

helm package helm-chart

helm lint helm-chart

mv helm-chart-x.x.x.tgz ./docs

helm repo index docs --url https://satovarr.github.io/helm-chart/

git add .

git commit -m "update chart"

git push origin master
```


## Pull and Update Chart
```bash
helm repo add helm-chart https://satovarr.github.io/helm-chart/
helm repo update
helm repo list
```


## Add to Argo
```bash
argocd app create helm-microservice --repo https://satovarr.github.io/helm-chart/ --helm-chart helm-chart --revision 0.1.0 --dest-namespace default --dest-server https://kubernetes.default.svc --sync-policy auto
```