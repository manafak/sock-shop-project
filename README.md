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

4. i created an Ingress controller using Helm.
An ingress controller was deployed to manage external access to the services within the Kubernetes cluster. This was done using Helm, a package manager for Kubernetes.
The ingress controller was responsible for creating a load balancer that would route traffic to the appropriate services within the cluster.
<img width="1119" alt="Screenshot 2024-08-04 at 12 18 00 AM" src="https://github.com/user-attachments/assets/a6d482b5-c5c1-403e-b730-8dbc35daffe4">
<img width="1192" alt="Screenshot 2024-08-04 at 12 30 07 AM" src="https://github.com/user-attachments/assets/b6496d95-5b23-4da0-bfe9-fbbb8f324ffb">

5. Map services to applications using an ingress file.
An ingress file was created to define routing rules. This file mapped external requests to the correct services running within the Kubernetes cluster.
When users accessed the domain, the ingress controller would direct them to the load balancer, which would then route the request to the appropriate cluster IP.

6. Deploy the Ingress-NGINX Controller using Helm.
The ingress-nginx controller was deployed using Helm, making it easier to manage and configure ingress resources.

7. Deploy Prometheus and Grafana using Helm.
Prometheus was deployed for logging, along with Grafana for monitoring. Helm was used to install the "prometheus/kube-prometheus-stack," which included Prometheus, Grafana, node exporter, kube-state-metrics, and Alertmanager.
<img width="1193" alt="Screenshot 2024-08-04 at 11 10 50 PM" src="https://github.com/user-attachments/assets/8dc595ab-a59d-4664-8fd4-e7b63241c16c">
<img width="1193" alt="Screenshot 2024-08-07 at 12 23 00 AM" src="https://github.com/user-attachments/assets/6a68fe84-a0a1-4d8e-b98e-b32ac45e4c15">
<img width="1428" alt="Screenshot 2024-08-08 at 11 06 28 AM" src="https://github.com/user-attachments/assets/5985cb5f-8ee7-45d0-8e17-ee9dd3d5b2e8">

8. Install Cert-Manager and Obtain HTTPS certificates.
Cert-manager was installed using Helm as well. Let’s Encrypt was used as the certificate provider.
This ensured that the application was accessible over HTTPS, enhancing security.
<img width="1196" alt="Screenshot 2024-08-10 at 10 41 12 PM" src="https://github.com/user-attachments/assets/3f429d31-699f-4c8b-bd48-d64c69ff9111">

9. Implemented CI/CD Pipeline using GitHub actions.
A CI/CD pipeline was implemented using GitHub Actions which is part of this repository, with two separate workflows:
The first workflow was responsible for creating the infrastructure and namespaces.
The second workflow handled the remaining deployment processes, including the deployment of applications, monitoring tools, and certificates. Deployment of both branches/workflow were successful
<img width="1200" alt="Screenshot 2024-08-14 at 12 38 59 PM" src="https://github.com/user-attachments/assets/c602a187-e2cd-4634-afb1-c328e9da9dcd">
