# vcd_catalog

[back](../vcd.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vcd = ">= 3.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vcd_catalog" {
  source = "./modules/vcd/r/vcd_catalog"

  # delete_force - (required) is a type of bool
  delete_force = null
  # delete_recursive - (required) is a type of bool
  delete_recursive = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # org - (optional) is a type of string
  org = null
  # storage_profile_id - (optional) is a type of string
  storage_profile_id = null
}
```

[top](#index)

### Variables

```terraform
variable "delete_force" {
  description = "(required) - When destroying use delete_force=True with delete_recursive=True to remove a catalog and any objects it contains, regardless of their state."
  type        = bool
}

variable "delete_recursive" {
  description = "(required) - When destroying use delete_recursive=True to remove the catalog and any objects it contains that are in a state that normally allows removal."
  type        = bool
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "org" {
  description = "(optional) - The name of organization to use, optional if defined at provider level. Useful when connected as sysadmin working across different organizations"
  type        = string
  default     = null
}

variable "storage_profile_id" {
  description = "(optional) - Optional storage profile ID"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vcd_catalog" "this" {
  # delete_force - (required) is a type of bool
  delete_force = var.delete_force
  # delete_recursive - (required) is a type of bool
  delete_recursive = var.delete_recursive
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # org - (optional) is a type of string
  org = var.org
  # storage_profile_id - (optional) is a type of string
  storage_profile_id = var.storage_profile_id
}
```

[top](#index)

### Outputs

```terraform
output "created" {
  description = "returns a string"
  value       = vcd_catalog.this.created
}

output "id" {
  description = "returns a string"
  value       = vcd_catalog.this.id
}

output "this" {
  value = vcd_catalog.this
}
```

[top](#index)