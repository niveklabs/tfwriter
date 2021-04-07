# nsxt_policy_realization_info

[back](../nsxt.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nsxt = ">= 3.1.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nsxt_policy_realization_info" {
  source = "./modules/nsxt/d/nsxt_policy_realization_info"

  # entity_type - (optional) is a type of string
  entity_type = null
  # path - (required) is a type of string
  path = null
  # site_path - (optional) is a type of string
  site_path = null
}
```

[top](#index)

### Variables

```terraform
variable "entity_type" {
  description = "(optional) - The entity type of the realized resource"
  type        = string
  default     = null
}

variable "path" {
  description = "(required) - The path for the policy resource"
  type        = string
}

variable "site_path" {
  description = "(optional) - Path of the site this resource belongs to"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "nsxt_policy_realization_info" "this" {
  # entity_type - (optional) is a type of string
  entity_type = var.entity_type
  # path - (required) is a type of string
  path = var.path
  # site_path - (optional) is a type of string
  site_path = var.site_path
}
```

[top](#index)

### Outputs

```terraform
output "entity_type" {
  description = "returns a string"
  value       = data.nsxt_policy_realization_info.this.entity_type
}

output "id" {
  description = "returns a string"
  value       = data.nsxt_policy_realization_info.this.id
}

output "realized_id" {
  description = "returns a string"
  value       = data.nsxt_policy_realization_info.this.realized_id
}

output "state" {
  description = "returns a string"
  value       = data.nsxt_policy_realization_info.this.state
}

output "this" {
  value = nsxt_policy_realization_info.this
}
```

[top](#index)