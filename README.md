![Texte alternatif](https://www.freelogovectors.net/wp-content/uploads/2018/11/kubernetes-logo.png)


## This repository contains the projects and exercises that I was able to perform on K8s during my training at Eazytraining



## 📁  TP2  📁
This exercise will be divided in 2 goals: 
- Write a pod.yml file to deploy a pod with the "mmumshad/simple-webapp-color" image  specifying that the desired color is red.
The application will be reachable on the 8080 port.
- Deploy 2 replicas of a nginx pod (in 1.18.0 version ) in the nginx-deployment.yml file.

You will find these 2 files in the repository



## 📁  TP3  📁

The main goal of this exercise is to create a Service of type NodePort

We will first create a namespace named "production" (all resources will be created in this namespace later).

Then, we will create 2 manifest files, to deploy two pods with the "mmumshad/simple-webapp-color" image  : one with the red color, the other with the blue color.
The pods will have the "app:web" label.

Finally we write a manifest service-node-port-web.yml to expose the pods on port 30008 



## 📁  TP4  📁


In this exercise we will discover the storage management in K8s.

- Volumes
We will first write a mysql-volume.yml manifest to deploy a Mysql pod with several environment variables (MYSQL_ROOT_PASSWORD, MYSQL_DATABASE, MYSQL_USER and MYSQL_PASSWORD)
We will make the folder containing the Mysql files (/var/lib/mysql) persistent by mounting it on our machine, under /data-volume

- Persistent Volume (PV) and Persistent Volume Claim (PVC)
We will create a PV (pv.yml) of 1 Gi using the local folder /data-pv to store the data, as well as a PVC of 100 Mi using this PV.
We will write a mysql-pv.yml manifest that will use our PVC.


## 📁  TP5 📁

We will install Helm v3 and use the wordpress chart to deploy this application.
We will override some variables (like "wordpressUsername" or
"wordpressPassword") using the values.yaml file to customize our deployment
So in this repository you will find the values.yaml and a Helm-v3.txt file which list all the commands using to perform this exercice

## 📁 Mini-projet 📁

The goal of this project is to deploy Wordpress using manifests (not Helm)

To perform this I have followed the next steps :

- create a namespace (wordpress-namespace.yml)
- write a file (app-wordpress-secret.yml) to manage sensitive data (wordpress_db_password, mysql_password ect...)
- create a Mysql deployment with one replica (mysql-deployment.yml)
- create a Wordpress deployment (wordpress-deployment.yml) with the right environment variables to connect to the mysql database 
- create a ClusterIP (service-clusterip-mysql.yml) service to expose the Mysql pod
- create of a Nodeport service (service-nodeport-wordpress.yml) to expose the Wordpress frontend


Also you will find a cheat sheet with some useful commands
