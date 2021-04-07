# rancher2_auth_config_azuread

[back](../rancher2.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    rancher2 = ">= 1.13.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "rancher2_auth_config_azuread" {
  source = "./modules/rancher2/r/rancher2_auth_config_azuread"

  # access_mode - (optional) is a type of string
  access_mode = null
  # allowed_principal_ids - (optional) is a type of list of string
  allowed_principal_ids = []
  # annotations - (optional) is a type of map of string
  annotations = {}
  # application_id - (required) is a type of string
  application_id = null
  # application_secret - (required) is a type of string
  application_secret = null
  # auth_endpoint - (required) is a type of string
  auth_endpoint = null
  # enabled - (optional) is a type of bool
  enabled = null
  # endpoint - (optional) is a type of string
  endpoint = null
  # graph_endpoint - (required) is a type of string
  graph_endpoint = null
  # labels - (optional) is a type of map of string
  labels = {}
  # rancher_url - (required) is a type of string
  rancher_url = null
  # tenant_id - (required) is a type of string
  tenant_id = null
  # token_endpoint - (required) is a type of string
  token_endpoint = null
}
```

[top](#index)

### Variables

```terraform
variable "access_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "allowed_principal_ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "annotations" {
  description = "(optional) - Annotations of the resource"
  type        = map(string)
  default     = null
}

variable "application_id" {
  description = "(required)"
  type        = string
}

variable "application_secret" {
  description = "(required)"
  type        = string
}

variable "auth_endpoint" {
  description = "(required)"
  type        = string
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "endpoint" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "graph_endpoint" {
  description = "(required)"
  type        = string
}

variable "labels" {
  description = "(optional) - Labels of the resource"
  type        = map(string)
  default     = null
}

variable "rancher_url" {
  description = "(required)"
  type        = string
}

variable "tenant_id" {
  description = "(required)"
  type        = string
}

variable "token_endpoint" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "rancher2_auth_config_azuread" "this" {
  # access_mode - (optional) is a type of string
  access_mode = var.access_mode
  # allowed_principal_ids - (optional) is a type of list of string
  allowed_principal_ids = var.allowed_principal_ids
  # annotations - (optional) is a type of map of string
  annotations = var.annotations
  # application_id - (required) is a type of string
  application_id = var.application_id
  # application_secret - (required) is a type of string
  application_secret = var.application_secret
  # auth_endpoint - (required) is a type of string
  auth_endpoint = var.auth_endpoint
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # endpoint - (optional) is a type of string
  endpoint = var.endpoint
  # graph_endpoint - (required) is a type of string
  graph_endpoint = var.graph_endpoint
  # labels - (optional) is a type of map of string
  labels = var.labels
  # rancher_url - (required) is a type of string
  rancher_url = var.rancher_url
  # tenant_id - (required) is a type of string
  tenant_id = var.tenant_id
  # token_endpoint - (required) is a type of string
  token_endpoint = var.token_endpoint
}
```

[top](#index)

### Outputs

```terraform
output "annotations" {
  description = "returns a map of string"
  value       = rancher2_auth_config_azuread.this.annotations
}

output "id" {
  description = "returns a string"
  value       = rancher2_auth_config_azuread.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = rancher2_auth_config_azuread.this.labels
}

output "name" {
  description = "returns a string"
  value       = rancher2_auth_config_azuread.this.name
}

output "type" {
  description = "returns a string"
  value       = rancher2_auth_config_azuread.this.type
}

output "this" {
  value = rancher2_auth_config_azuread.this
}
```

[top](#index)