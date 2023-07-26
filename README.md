# yelb voting app deployed on kubenetes
<img src="https://github.com/dreamwalkz/yelb/blob/main/screenshot.png">

^^^shell
kubectl -n yelb describe pod $(kubectl -n yelb get pods | grep yelb-ui | awk '{print $1}') | grep "Node"
^^^
