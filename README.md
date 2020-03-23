# Install Dashboard on kubernetes

useful link
````
https://github.com/kubernetes/dashboard/blob/master/docs/user/access-control/creating-sample-user.md
````


## To install the dashboard use the following command
````
kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.0.0-rc6/aio/deploy/recommended.yaml
````


## create a service account

````
kubectl apply -f serviceAccount.yaml
````




## create a Clusterwide role binding

````
kubectl apply -f RoleBinding.yaml
````

## run proxy to reach dashboard
````
kubectl proxy
````


## Use the below comand to get the login token
````
kubectl -n kubernetes-dashboard describe secret $(kubectl -n kubernetes-dashboard get secret | grep admin-user | awk '{print $1}')
````

