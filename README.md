To-Do App

---------------
This is a simple To-Do list application that helps users manage tasks. The app is built using the following technologies and can be deployed using Docker Swarm or Azure Kubernetes Service (AKS).

Technologies Used:

Backend: Python (Flask)

Database: SQLite

Containerization: Docker

Container Orchestration: Docker Swarm, Azure Kubernetes Service (AKS)

Cloud Providers: Azure

--------------------
Prerequisites:

Before deploying the app, ensure you have the following installed:

Docker

Azure CLI

kubectl

------------------
Docker Image:

The app is packaged as a Docker image and is available on Docker Hub:

    docker pull surajkk93/todo-app:latest
-------------------------------
How to Deploy on Docker Swarm

You can deploy this To-Do app on Docker Swarm for local or production environments. Follow these steps:

Steps:
1. Initialize Docker Swarm: If you haven't initialized Docker Swarm, run the following on your server:
   
   `docker swarm init`
2. Create a Stack File (docker-compose.yml): Create a docker-compose.yml file to define the services:
3. Deploy the Stack: Use docker stack deploy to deploy the application to the Swarm:

   `docker stack deploy -c docker-compose.yml todo-app`
5. Check the Service: To verify that your service is running, run:

    `docker service ls`
7. Access the Application: Access the app through your server's IP address on port 80:
 
  `http://localhost:5000`

-----------------------------------------------
How to Deploy on AKS (Azure Kubernetes Service)

You can deploy the same app on Azure Kubernetes Service (AKS) for cloud hosting.

Steps:

1.Create Resource Group: First, create a resource group to hold your AKS resources:
 
  `az group create --name myResourceGroup --location eastus`
  
2.Create AKS Cluster: Create an AKS cluster with the following command:
  
 `az aks create --resource-group myResourceGroup --name myAKSCluster --node-count 1 --enable-addons monitoring --generate-ssh-keys`
 
3.Connect to AKS Cluster: Configure kubectl to connect to your AKS cluster:

 ` az aks get-credentials --resource-group myResourceGroup --name myAKSCluster`
 
4.Create a Kubernetes Deployment: Create a Kubernetes deployment YAML file (todo-app-deployment.yaml):

5.Deploy the Application: Apply the deployment using the following command:
 
 ` kubectl apply -f todo-app-deployment.yaml`
 
6.Get External IP: Once the service is deployed, get the external IP to access the application:
  
  `kubectl get service todo-app-service`
  
7.Visit the external IP in your browser to access the application.


___________________________________________________________________________________________________________________________


License
This project is licensed under the MIT License - see the LICENSE file for details.

This README provides a clear overview and steps for deployment. Let me know if you'd like to add or modify anything!











