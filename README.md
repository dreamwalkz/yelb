# Yet Another Sample App on Kubenetes.

Voting UI Frontend, Application Server, Database Server and Caching Service using Redis.app deployed on kubenetes

<img src="https://github.com/dreamwalkz/yelb/blob/main/showcase.gif">

NodePort Deployment:

To access the application, open web browser to http://<ip>:30001

```shell
kubectl -n yelb describe pod $(kubectl -n yelb get pods | grep yelb-ui | awk '{print $1}') | grep "Node"
```

LoadBalancer Service Deployment:

Step 1 - Deploy the application

```shell
kubectl create ns yelb
kubectl apply -f https://raw.githubusercontent.com/dreamwalkz/yelb/main/yelb-lb.yaml
```

Step 2 - Verify all pods are ready

```shell
kubectl -n yelb get pods
```

Step 3 - To access the application, open web browser to http://<external-ip>

```shell
kubectl -n yelb get svc/yelb-ui
```


