# sock-shop-project

Project Overview:
This project involved deploying a microservices-based application, specifically the Socks Shop, on Kubernetes using Infrastructure as Code. The goal was to automate and streamline a deployment process, ensuring it was both efficient and secure.

Execution Steps:
1. I Create a Cluster on AWS Using EKS Terraform Modules
The first step was 1 set up an Amazon EKS cluster using Terraform, an iaac tool. Terraform modules specific to EKS were utilized to provision the cluster efficiently.
This involved defining the necessary resources such as nodes, networking configurations, and other cluster-related settings in Terraform configuration files.
<img width="1196" alt="Screenshot 2024-08-03 at 2 55 13 PM" src="https://github.com/user-attachments/assets/9ba83c1d-cd79-4200-9159-3e0063b640f6">


2. Creating a VPC for the Cluster
Before deploying the EKS cluster, a Virtual Private Cloud (VPC) was created using Terraform. The VPC provided isolated networking for the cluster, including subnets, route tables, and internet gateways.
This ensured the Kubernetes cluster had a secure and scalable network environment.

