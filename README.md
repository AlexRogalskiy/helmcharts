# helmcharts
A Helm chart repo

## How to include this chart in your Helm repos
```
helm repo add mkretz https://mkretz.github.com/helmcharts
```


## How to make a new version of a helm chart submodule
Let's take the notification-k8s submodule as an example

1. Pull the latest changes of the submodule: 
```
cd notification-k8s
git pull
```
2. Package the helm chart
```
helm package notification-k8s
```
3. Move the packaged chart to the docs directory
```
mv notification-k8s-x.y.z.tgz docs
```
4. Rebuild the repo index
```
helm repo index docs --url https://mkretz.github.com/helmcharts
```
5. Push the changes
```
git add .
git commit -m "New version of notification-k8s"
git push
```
