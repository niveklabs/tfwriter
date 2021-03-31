# lacework_integration_docker_v2

[back](../lacework.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    lacework = ">= 0.3.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "lacework_integration_docker_v2" {
  source = "./modules/lacework/r/lacework_integration_docker_v2"

  # enabled - (optional) is a type of bool
  enabled = null
  # limit_by_label - (optional) is a type of string
  limit_by_label = null
  # limit_by_tag - (optional) is a type of string
  limit_by_tag = null
  # name - (required) is a type of string
  name = null
  # password - (required) is a type of string
  password = null
  # registry_domain - (required) is a type of string
  registry_domain = null
  # ssl - (optional) is a type of bool
  ssl = null
  # username - (required) is a type of string
  username = null
}
```

[top](#index)

### Variables

```terraform
variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "limit_by_label" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "limit_by_tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "password" {
  description = "(required)"
  type        = string
}

variable "registry_domain" {
  description = "(required)"
  type        = string
}

variable "ssl" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "username" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "lacework_integration_docker_v2" "this" {
  enabled         = var.enabled
  limit_by_label  = var.limit_by_label
  limit_by_tag    = var.limit_by_tag
  name            = var.name
  password        = var.password
  registry_domain = var.registry_domain
  ssl             = var.ssl
  username        = var.username
}
```

[top](#index)

### Outputs

```terraform
output "created_or_updated_by" {
  description = "returns a string"
  value       = lacework_integration_docker_v2.this.created_or_updated_by
}

output "created_or_updated_time" {
  description = "returns a string"
  value       = lacework_integration_docker_v2.this.created_or_updated_time
}

output "id" {
  description = "returns a string"
  value       = lacework_integration_docker_v2.this.id
}

output "intg_guid" {
  description = "returns a string"
  value       = lacework_integration_docker_v2.this.intg_guid
}

output "org_level" {
  description = "returns a bool"
  value       = lacework_integration_docker_v2.this.org_level
}

output "type_name" {
  description = "returns a string"
  value       = lacework_integration_docker_v2.this.type_name
}

output "this" {
  value = lacework_integration_docker_v2.this
}
```

[top](#index)