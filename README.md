# sock-shop-project

Project Overview:
This project involved deploying a microservices-based application, specifically the Socks Shop, on Kubernetes using Infrastructure as Code. The goal was to automate and streamline a deployment process, ensuring it was both efficient and secure.

Execution Steps:
1. I create a cluster on AWS using EKS terraform modules.
The first step was 1 set up an Amazon EKS cluster using Terraform, an iaac tool. Terraform modules specific to EKS were utilized to provision the cluster efficiently.
This involved defining the necessary resources such as nodes, networking configurations, and other cluster-related settings in Terraform configuration files.
<img width="1196" alt="Screenshot 2024-08-03 at 2 55 13 PM" src="https://github.com/user-attachments/assets/9ba83c1d-cd79-4200-9159-3e0063b640f6">


2. Creating a VPC for the cluster.
Before deploying the EKS cluster, a Virtual Private Cloud (VPC) was created using Terraform. The VPC provided isolated networking for the cluster, including subnets, route tables, and internet gateways.
This ensured the Kubernetes cluster had a secure and scalable network environment.

3. i retrieve EKS configuration files from the provided git repo.
The necessary EKS configuration files were obtained from the provided GitHub repository. These files contained predefined settings and templates needed for deploying the Socks Shop application. (file.yaml) in the manifest directory.

4. i created an Ingress controller using Helm
An ingress controller was deployed to manage external access to the services within the Kubernetes cluster. This was done using Helm, a package manager for Kubernetes.
The ingress controller was responsible for creating a load balancer that would route traffic to the appropriate services within the cluster.
<img width="1119" alt="Screenshot 2024-08-04 at 12 18 00 AM" src="https://github.com/user-attachments/assets/a6d482b5-c5c1-403e-b730-8dbc35daffe4">
<img width="1192" alt="Screenshot 2024-08-04 at 12 30 07 AM" src="https://github.com/user-attachments/assets/b6496d95-5b23-4da0-bfe9-fbbb8f324ffb">
