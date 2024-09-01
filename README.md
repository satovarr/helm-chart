```bash
make the changes in chart

helm package helm-chart

helm lint helm-chart

mv helm-chart-x.x.x.tgz ./docs

helm repo index docs --url https://raw.githubusercontent.com/username/repo/master/docs TODO change

git add .

git commit -m "update chart"

git push origin master
```