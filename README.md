
# GCP final project

deploying static web app on GCP







## Deployment

To deploy this project run

```terraform
  run the following commands :
  terraform init
  terraform apply
```
at the end of infra structure creation you will get 2 gcloud commands:

1- to ssh to bastion

2- to connect to cluster 

![App Screenshot](https://github.com/EbraamMaher/Infra/blob/master/pictures/3.png)


##### prepare the bastion

###### after ssh to vm you in order to prepare the vm to build and deploy you have to install these tools:

1- install docker  : https://docs.docker.com/engine/install/debian/
2- install keubctl : https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/

###### then authenticate your account : 
```gcloud
   gcloud auth login
```

###### then connect to the cluster using the **2nd command printed out** after terraform created all resources.


##### check :
![App Screenshot](https://github.com/EbraamMaher/Infra/blob/master/pictures/4.png)
![App Screenshot](https://github.com/EbraamMaher/Infra/blob/master/pictures/5.png)



then you can build and push the image to GCR using these instructions:
https://cloud.google.com/container-registry/docs/pushing-and-pulling

after that Deployment stage using kubectl

by getting the external ip and port you can access the app :

```kuebctl 
  kubectl get pods -n app
  kubectl get svc -n app
```
###### then access the App using url : http://external_ip:port
![App Screenshot](https://github.com/EbraamMaher/GCP-fproject/blob/master/pictures/10.png)
![App Screenshot](https://github.com/EbraamMaher/GCP-fproject/blob/master/pictures/11.png)
