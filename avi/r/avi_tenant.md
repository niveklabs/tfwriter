# avi_tenant

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    avi = ">= 0.2.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "avi_tenant" {
  source = "./modules/avi/r/avi_tenant"

  # created_by - (optional) is a type of string
  created_by = null
  # description - (optional) is a type of string
  description = null
  # local - (optional) is a type of bool
  local = null
  # name - (required) is a type of string
  name = null
  # uuid - (optional) is a type of string
  uuid = null

  config_settings = [{
    se_in_provider_context       = null
    tenant_access_to_provider_se = null
    tenant_vrf                   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "created_by" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "local" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "config_settings" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      se_in_provider_context       = bool
      tenant_access_to_provider_se = bool
      tenant_vrf                   = bool
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_tenant" "this" {
  # created_by - (optional) is a type of string
  created_by = var.created_by
  # description - (optional) is a type of string
  description = var.description
  # local - (optional) is a type of bool
  local = var.local
  # name - (required) is a type of string
  name = var.name
  # uuid - (optional) is a type of string
  uuid = var.uuid

  dynamic "config_settings" {
    for_each = var.config_settings
    content {
      # se_in_provider_context - (optional) is a type of bool
      se_in_provider_context = config_settings.value["se_in_provider_context"]
      # tenant_access_to_provider_se - (optional) is a type of bool
      tenant_access_to_provider_se = config_settings.value["tenant_access_to_provider_se"]
      # tenant_vrf - (optional) is a type of bool
      tenant_vrf = config_settings.value["tenant_vrf"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "created_by" {
  description = "returns a string"
  value       = avi_tenant.this.created_by
}

output "description" {
  description = "returns a string"
  value       = avi_tenant.this.description
}

output "id" {
  description = "returns a string"
  value       = avi_tenant.this.id
}

output "uuid" {
  description = "returns a string"
  value       = avi_tenant.this.uuid
}

output "this" {
  value = avi_tenant.this
}
```

[top](#index)