# lacework_integration_docker_hub

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
module "lacework_integration_docker_hub" {
  source = "./modules/lacework/r/lacework_integration_docker_hub"

  # enabled - (optional) is a type of bool
  enabled = null
  # limit_by_label - (optional) is a type of string
  limit_by_label = null
  # limit_by_repos - (optional) is a type of string
  limit_by_repos = null
  # limit_by_tag - (optional) is a type of string
  limit_by_tag = null
  # limit_num_imgs - (optional) is a type of number
  limit_num_imgs = null
  # name - (required) is a type of string
  name = null
  # password - (required) is a type of string
  password = null
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

variable "limit_by_repos" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "limit_by_tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "limit_num_imgs" {
  description = "(optional)"
  type        = number
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

variable "username" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "lacework_integration_docker_hub" "this" {
  enabled        = var.enabled
  limit_by_label = var.limit_by_label
  limit_by_repos = var.limit_by_repos
  limit_by_tag   = var.limit_by_tag
  limit_num_imgs = var.limit_num_imgs
  name           = var.name
  password       = var.password
  username       = var.username
}
```

[top](#index)

### Outputs

```terraform
output "created_or_updated_by" {
  description = "returns a string"
  value       = lacework_integration_docker_hub.this.created_or_updated_by
}

output "created_or_updated_time" {
  description = "returns a string"
  value       = lacework_integration_docker_hub.this.created_or_updated_time
}

output "id" {
  description = "returns a string"
  value       = lacework_integration_docker_hub.this.id
}

output "intg_guid" {
  description = "returns a string"
  value       = lacework_integration_docker_hub.this.intg_guid
}

output "org_level" {
  description = "returns a bool"
  value       = lacework_integration_docker_hub.this.org_level
}

output "type_name" {
  description = "returns a string"
  value       = lacework_integration_docker_hub.this.type_name
}

output "this" {
  value = lacework_integration_docker_hub.this
}
```

[top](#index)