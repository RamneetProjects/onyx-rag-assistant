# Onyx RAG Assistant on AWS

An end-to-end DevOps and GitOps project deploying the Onyx RAG application
on AWS Kubernetes infrastructure.

## Architecture

- AWS: ap-south-1 (Mumbai)
- Infrastructure as Code: Terraform
- Configuration management: Ansible
- Container orchestration: Amazon EKS
- Container registry: Amazon ECR
- Application packaging: Official Onyx Helm chart
- GitOps: Argo CD
- CI: GitHub Actions
- Metrics: Prometheus
- Dashboards: Grafana
- Logs: Loki
- Alerting: Alertmanager
- AWS monitoring: CloudWatch
- LLM provider: OpenAI API

Onyx is self-hosted. LLM inference and embeddings use cloud APIs.
No local LLM inference is part of this project.

## Repository layout

```text
application/       Onyx Helm values and application configuration
terraform/         AWS infrastructure modules and environments
ansible/           Configuration management and operational playbooks
kubernetes/        Argo CD applications and Kubernetes configuration
monitoring/        Prometheus, Grafana, Loki and Alertmanager
.github/workflows/ CI workflows
scripts/           Developer and operations scripts
docs/              Architecture, setup and operations documentation
tests/             Validation and acceptance tests
