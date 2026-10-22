Hello, I'm Daniele Gattoni, Cloud DevOps Engineer | Platform Architecture & Infrastructure, and this is my engineering portfolio!  
This organization hosts **NovaCommerce** and other production-grade, enterprise-level infrastructure projects designed to showcase modern DevOps best practices, multi-region high availability, and GitOps workflows.

## Featured Projects & Architectures

### 1. [NovaCommerce: Multi-Region AWS EKS GitOps & LGTM Observability Platform](https://github.com/novacommerce/novacommerce-devops-infra)
A **Gold Standard** infrastructure platform engineered with **Terraform 1.10+** and **Terragrunt** following the Composite Module (Stack) pattern for multi-region deployment.

* **Multi-Region Architecture:** Primary cluster deployed in AWS Frankfurt (`eu-central-1`) with high-availability Disaster Recovery in Ireland (`eu-west-1`).
* **Kubernetes Orchestration:** EKS Clusters with **Karpenter** for dynamic autoscaling across 3 Availability Zones (AZs).
* **Observability (Grafana LGTM Stack):** Alloy, Mimir, Tempo, and Loki configured with IRSA (IAM Roles for Service Accounts) writing directly to region-isolated S3 buckets.
* **Security & State Management:** Zero-trust network segmentation (Public ALB/NAT Gateways vs Private Worker Nodes), S3 native state locking (`use_lockfile = true`), and AWS Secrets Manager integration.

<img width="2400" height="855" alt="novacommerce diagrams" src="https://github.com/user-attachments/assets/db36b6dd-9097-49ca-9ac0-a8a2d0009325" />

## Microservices Ecosystem

The NovaCommerce platform comprises modern, containerized microservices hosted on AWS ECR:

*  **`novacommerce-svc-auth`** – Authentication & Authorization
*  **`novacommerce-svc-catalog`** – Product Catalog Management
*  **`novacommerce-svc-order`** – Order Processing & Checkout
*  **`novacommerce-svc-payment`** – Payment Gateway Integration

## End-to-End Web Request Flow

Here is the path a web request follows, from opening the NovaCommerce website to reaching the container of the correct microservice.  

<img width="4321" height="1728" alt="diagramma viaggio web request" src="https://github.com/user-attachments/assets/568565a2-1466-4677-8d64-b0c4d5d99c95" />

## Disaster Recovery Strategy

For this architecture, we choose a Warm Standby / Active-Passive disaster recovery strategy.  

---

### 2. [Ansible Command Center with Semaphore](https://github.com/novacommerce/ansible-command-center)
An automated configuration management and orchestration control plane powered by **Semaphore UI** and **Ansible**.

* **Centralized Playbook Execution:** Web UI and REST API for triggering Ansible automation workflows across multi-environment targets.
* **Role-Based Access Control (RBAC):** Fine-grained permission management, secrets vaulting, and execution logging.
* **CI/CD Integration:** Automated infrastructure drift remediation and server provisioning triggered via Webhooks.

---
## 📊 Project Governance & Kanban

Project roadmaps, sprint planning, and active tasks are managed via our centralized **[GitHub Projects Board](https://github.com/orgs/novacommerce/projects)**.
