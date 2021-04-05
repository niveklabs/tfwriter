# rancher2_auth_config_github

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
module "rancher2_auth_config_github" {
  source = "./modules/rancher2/r/rancher2_auth_config_github"

  # access_mode - (optional) is a type of string
  access_mode = null
  # allowed_principal_ids - (optional) is a type of list of string
  allowed_principal_ids = []
  # annotations - (optional) is a type of map of string
  annotations = {}
  # client_id - (required) is a type of string
  client_id = null
  # client_secret - (required) is a type of string
  client_secret = null
  # enabled - (optional) is a type of bool
  enabled = null
  # hostname - (optional) is a type of string
  hostname = null
  # labels - (optional) is a type of map of string
  labels = {}
  # tls - (optional) is a type of bool
  tls = null
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

variable "client_id" {
  description = "(required)"
  type        = string
}

variable "client_secret" {
  description = "(required)"
  type        = string
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "hostname" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional) - Labels of the resource"
  type        = map(string)
  default     = null
}

variable "tls" {
  description = "(optional)"
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "rancher2_auth_config_github" "this" {
  access_mode           = var.access_mode
  allowed_principal_ids = var.allowed_principal_ids
  annotations           = var.annotations
  client_id             = var.client_id
  client_secret         = var.client_secret
  enabled               = var.enabled
  hostname              = var.hostname
  labels                = var.labels
  tls                   = var.tls
}
```

[top](#index)

### Outputs

```terraform
output "annotations" {
  description = "returns a map of string"
  value       = rancher2_auth_config_github.this.annotations
}

output "id" {
  description = "returns a string"
  value       = rancher2_auth_config_github.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = rancher2_auth_config_github.this.labels
}

output "name" {
  description = "returns a string"
  value       = rancher2_auth_config_github.this.name
}

output "type" {
  description = "returns a string"
  value       = rancher2_auth_config_github.this.type
}

output "this" {
  value = rancher2_auth_config_github.this
}
```

[top](#index)