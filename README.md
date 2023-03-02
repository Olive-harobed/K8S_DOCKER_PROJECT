# K8S_DOCKER_PROJECT
## Portfolio Website Deployment on Docker Registry and EKS

This is a simple personal website project deployed on Amazon Elastic Kubernetes Service (EKS) using Nginx container image. The website is publicly accessible through a Load balancer DNS.

### Prerequisites
- AWS account
- AWS CLI installed and configured
- kubectl installed
- Docker installed
- Git installed
- Basic knowledge of Kubernetes and Docker

### Steps

1. Clone the project from the Github repository or go to the folder which contains the files required to set up the website e.g html and css files:
`git clone <repository-url>` / `cd <folder-name>`
2. Build the Docker image:
`docker build -t <image-name> . `
3. Push the Docker image to your container registry:
`docker push <image-name>`
4. Create an EKS cluster with at least 2 nodes in your AWS account.
5. Apply the Kubernetes manifests:
`kubectl apply -f <deployment_file>`
`kubectl apply -f <service_file>`
Note that the pod.yaml files are not to be applied when using a deployment. Applying the service and pod files can provision a publicly accessible website but do not have the advantages of replication and scalability among other advantages that running a deployment
This will create the deployment and service resources needed to run the website on your EKS cluster.
Wait for the resources to be provisioned and the website to become publicly accessible. This may take a few minutes.
Once the website is accessible, open a web browser and access the website using the load balancer DNS.

![k8s-web](https://user-images.githubusercontent.com/79452458/222347172-cd416a42-70bf-424e-8a2a-e7616b1afb6f.jpg)

### Conclusion
In this project, we have created a simple personal website using Nginx container image, deployed it on Amazon Elastic Kubernetes Service (EKS) with a load balancer. This project can be used as a template for deploying other containerized web applications on EKS.


