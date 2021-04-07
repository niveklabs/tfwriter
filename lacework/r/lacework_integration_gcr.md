# lacework_integration_gcr

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
module "lacework_integration_gcr" {
  source = "./modules/lacework/r/lacework_integration_gcr"

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

  credentials = [{
    client_email   = null
    client_id      = null
    private_key    = null
    private_key_id = null
  }]
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

variable "registry_domain" {
  description = "(required)"
  type        = string
}

variable "credentials" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      client_email   = string
      client_id      = string
      private_key    = string
      private_key_id = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "lacework_integration_gcr" "this" {
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # limit_by_label - (optional) is a type of string
  limit_by_label = var.limit_by_label
  # limit_by_repos - (optional) is a type of string
  limit_by_repos = var.limit_by_repos
  # limit_by_tag - (optional) is a type of string
  limit_by_tag = var.limit_by_tag
  # limit_num_imgs - (optional) is a type of number
  limit_num_imgs = var.limit_num_imgs
  # name - (required) is a type of string
  name = var.name
  # registry_domain - (required) is a type of string
  registry_domain = var.registry_domain

  dynamic "credentials" {
    for_each = var.credentials
    content {
      # client_email - (required) is a type of string
      client_email = credentials.value["client_email"]
      # client_id - (required) is a type of string
      client_id = credentials.value["client_id"]
      # private_key - (required) is a type of string
      private_key = credentials.value["private_key"]
      # private_key_id - (required) is a type of string
      private_key_id = credentials.value["private_key_id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "created_or_updated_by" {
  description = "returns a string"
  value       = lacework_integration_gcr.this.created_or_updated_by
}

output "created_or_updated_time" {
  description = "returns a string"
  value       = lacework_integration_gcr.this.created_or_updated_time
}

output "id" {
  description = "returns a string"
  value       = lacework_integration_gcr.this.id
}

output "intg_guid" {
  description = "returns a string"
  value       = lacework_integration_gcr.this.intg_guid
}

output "org_level" {
  description = "returns a bool"
  value       = lacework_integration_gcr.this.org_level
}

output "type_name" {
  description = "returns a string"
  value       = lacework_integration_gcr.this.type_name
}

output "this" {
  value = lacework_integration_gcr.this
}
```

[top](#index)