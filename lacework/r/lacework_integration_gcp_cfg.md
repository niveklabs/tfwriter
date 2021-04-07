# lacework_integration_gcp_cfg

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
module "lacework_integration_gcp_cfg" {
  source = "./modules/lacework/r/lacework_integration_gcp_cfg"

  # enabled - (optional) is a type of bool
  enabled = null
  # name - (required) is a type of string
  name = null
  # resource_id - (required) is a type of string
  resource_id = null
  # resource_level - (optional) is a type of string
  resource_level = null
  # retries - (optional) is a type of number
  retries = null

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

variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_id" {
  description = "(required)"
  type        = string
}

variable "resource_level" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "retries" {
  description = "(optional) - The number of attempts to create the external integration."
  type        = number
  default     = null
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
resource "lacework_integration_gcp_cfg" "this" {
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # name - (required) is a type of string
  name = var.name
  # resource_id - (required) is a type of string
  resource_id = var.resource_id
  # resource_level - (optional) is a type of string
  resource_level = var.resource_level
  # retries - (optional) is a type of number
  retries = var.retries

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
  value       = lacework_integration_gcp_cfg.this.created_or_updated_by
}

output "created_or_updated_time" {
  description = "returns a string"
  value       = lacework_integration_gcp_cfg.this.created_or_updated_time
}

output "id" {
  description = "returns a string"
  value       = lacework_integration_gcp_cfg.this.id
}

output "intg_guid" {
  description = "returns a string"
  value       = lacework_integration_gcp_cfg.this.intg_guid
}

output "org_level" {
  description = "returns a bool"
  value       = lacework_integration_gcp_cfg.this.org_level
}

output "type_name" {
  description = "returns a string"
  value       = lacework_integration_gcp_cfg.this.type_name
}

output "this" {
  value = lacework_integration_gcp_cfg.this
}
```

[top](#index)