# lacework_integration_ecr

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
    lacework = ">= 0.2.7"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "lacework_integration_ecr" {
  source = "./modules/lacework/r/lacework_integration_ecr"

  # access_key_id - (required) is a type of string
  access_key_id = null
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
  # registry_domain - (required) is a type of string
  registry_domain = null
  # secret_access_key - (required) is a type of string
  secret_access_key = null
}
```

[top](#index)

### Variables

```terraform
variable "access_key_id" {
  description = "(required)"
  type        = string
}

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

variable "registry_domain" {
  description = "(required)"
  type        = string
}

variable "secret_access_key" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "lacework_integration_ecr" "this" {
  access_key_id     = var.access_key_id
  enabled           = var.enabled
  limit_by_label    = var.limit_by_label
  limit_by_repos    = var.limit_by_repos
  limit_by_tag      = var.limit_by_tag
  limit_num_imgs    = var.limit_num_imgs
  name              = var.name
  registry_domain   = var.registry_domain
  secret_access_key = var.secret_access_key
}
```

[top](#index)

### Outputs

```terraform
output "created_or_updated_by" {
  description = "returns a string"
  value       = lacework_integration_ecr.this.created_or_updated_by
}

output "created_or_updated_time" {
  description = "returns a string"
  value       = lacework_integration_ecr.this.created_or_updated_time
}

output "id" {
  description = "returns a string"
  value       = lacework_integration_ecr.this.id
}

output "intg_guid" {
  description = "returns a string"
  value       = lacework_integration_ecr.this.intg_guid
}

output "org_level" {
  description = "returns a bool"
  value       = lacework_integration_ecr.this.org_level
}

output "type_name" {
  description = "returns a string"
  value       = lacework_integration_ecr.this.type_name
}

output "this" {
  value = lacework_integration_ecr.this
}
```

[top](#index)