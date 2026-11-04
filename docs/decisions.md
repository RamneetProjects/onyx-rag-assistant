# Architecture decisions

## ADR-001: OpenAI as the only LLM provider

Decision:
Use OpenAI API for chat inference and embeddings.

Reason:
The project removes local LLM inference and keeps one cloud provider.

## ADR-002: Amazon EKS

Decision:
Use Amazon EKS for the AWS Kubernetes deployment.

Reason:
Demonstrates managed Kubernetes operations and GitOps deployment.

Cost constraint:
EKS is not suitable for a continuously running environment under
USD 30/month. Use a temporary lab and destroy it after testing.

## ADR-003: Official Onyx Helm chart

Decision:
Use the official Onyx Helm chart rather than recreating all application
workloads manually.

Reason:
The chart packages the supported Onyx services and configuration.

## ADR-004: Argo CD for application delivery

Decision:
Use Argo CD as the Kubernetes deployment reconciler.

Reason:
Git is the source of truth for application configuration.

GitHub Actions validates and publishes changes. Argo CD deploys them.

## ADR-005: Terraform and Ansible responsibilities

Decision:
Terraform provisions cloud resources. Ansible configures supporting
hosts and operational prerequisites.

Reason:
Avoid overlapping ownership and configuration drift.
