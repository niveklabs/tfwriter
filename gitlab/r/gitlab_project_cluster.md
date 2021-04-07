# gitlab_project_cluster

[back](../gitlab.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    gitlab = ">= 3.6.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "gitlab_project_cluster" {
  source = "./modules/gitlab/r/gitlab_project_cluster"

  # domain - (optional) is a type of string
  domain = null
  # enabled - (optional) is a type of bool
  enabled = null
  # environment_scope - (optional) is a type of string
  environment_scope = null
  # kubernetes_api_url - (required) is a type of string
  kubernetes_api_url = null
  # kubernetes_authorization_type - (optional) is a type of string
  kubernetes_authorization_type = null
  # kubernetes_ca_cert - (optional) is a type of string
  kubernetes_ca_cert = null
  # kubernetes_namespace - (optional) is a type of string
  kubernetes_namespace = null
  # kubernetes_token - (required) is a type of string
  kubernetes_token = null
  # managed - (optional) is a type of bool
  managed = null
  # management_project_id - (optional) is a type of string
  management_project_id = null
  # name - (required) is a type of string
  name = null
  # project - (required) is a type of string
  project = null
}
```

[top](#index)

### Variables

```terraform
variable "domain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "environment_scope" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "kubernetes_api_url" {
  description = "(required)"
  type        = string
}

variable "kubernetes_authorization_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "kubernetes_ca_cert" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "kubernetes_namespace" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "kubernetes_token" {
  description = "(required)"
  type        = string
}

variable "managed" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "management_project_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "project" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "gitlab_project_cluster" "this" {
  # domain - (optional) is a type of string
  domain = var.domain
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # environment_scope - (optional) is a type of string
  environment_scope = var.environment_scope
  # kubernetes_api_url - (required) is a type of string
  kubernetes_api_url = var.kubernetes_api_url
  # kubernetes_authorization_type - (optional) is a type of string
  kubernetes_authorization_type = var.kubernetes_authorization_type
  # kubernetes_ca_cert - (optional) is a type of string
  kubernetes_ca_cert = var.kubernetes_ca_cert
  # kubernetes_namespace - (optional) is a type of string
  kubernetes_namespace = var.kubernetes_namespace
  # kubernetes_token - (required) is a type of string
  kubernetes_token = var.kubernetes_token
  # managed - (optional) is a type of bool
  managed = var.managed
  # management_project_id - (optional) is a type of string
  management_project_id = var.management_project_id
  # name - (required) is a type of string
  name = var.name
  # project - (required) is a type of string
  project = var.project
}
```

[top](#index)

### Outputs

```terraform
output "cluster_type" {
  description = "returns a string"
  value       = gitlab_project_cluster.this.cluster_type
}

output "created_at" {
  description = "returns a string"
  value       = gitlab_project_cluster.this.created_at
}

output "id" {
  description = "returns a string"
  value       = gitlab_project_cluster.this.id
}

output "platform_type" {
  description = "returns a string"
  value       = gitlab_project_cluster.this.platform_type
}

output "provider_type" {
  description = "returns a string"
  value       = gitlab_project_cluster.this.provider_type
}

output "this" {
  value = gitlab_project_cluster.this
}
```

[top](#index)