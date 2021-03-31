# gitlab_group_cluster

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
    gitlab = ">= 3.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "gitlab_group_cluster" {
  source = "./modules/gitlab/r/gitlab_group_cluster"

  # domain - (optional) is a type of string
  domain = null
  # enabled - (optional) is a type of bool
  enabled = null
  # environment_scope - (optional) is a type of string
  environment_scope = null
  # group - (required) is a type of string
  group = null
  # kubernetes_api_url - (required) is a type of string
  kubernetes_api_url = null
  # kubernetes_authorization_type - (optional) is a type of string
  kubernetes_authorization_type = null
  # kubernetes_ca_cert - (optional) is a type of string
  kubernetes_ca_cert = null
  # kubernetes_token - (required) is a type of string
  kubernetes_token = null
  # managed - (optional) is a type of bool
  managed = null
  # management_project_id - (optional) is a type of string
  management_project_id = null
  # name - (required) is a type of string
  name = null
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

variable "group" {
  description = "(required)"
  type        = string
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
```

[top](#index)

### Resource

```terraform
resource "gitlab_group_cluster" "this" {
  domain                        = var.domain
  enabled                       = var.enabled
  environment_scope             = var.environment_scope
  group                         = var.group
  kubernetes_api_url            = var.kubernetes_api_url
  kubernetes_authorization_type = var.kubernetes_authorization_type
  kubernetes_ca_cert            = var.kubernetes_ca_cert
  kubernetes_token              = var.kubernetes_token
  managed                       = var.managed
  management_project_id         = var.management_project_id
  name                          = var.name
}
```

[top](#index)

### Outputs

```terraform
output "cluster_type" {
  description = "returns a string"
  value       = gitlab_group_cluster.this.cluster_type
}

output "created_at" {
  description = "returns a string"
  value       = gitlab_group_cluster.this.created_at
}

output "id" {
  description = "returns a string"
  value       = gitlab_group_cluster.this.id
}

output "platform_type" {
  description = "returns a string"
  value       = gitlab_group_cluster.this.platform_type
}

output "provider_type" {
  description = "returns a string"
  value       = gitlab_group_cluster.this.provider_type
}

output "this" {
  value = gitlab_group_cluster.this
}
```

[top](#index)