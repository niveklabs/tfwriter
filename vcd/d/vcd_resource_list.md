# vcd_resource_list

[back](../vcd.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "vcd_resource_list" {
  source = "./modules/vcd/d/vcd_resource_list"

  # list_mode - (optional) is a type of string
  list_mode = null
  # name - (required) is a type of string
  name = null
  # name_id_separator - (optional) is a type of string
  name_id_separator = null
  # org - (optional) is a type of string
  org = null
  # parent - (optional) is a type of string
  parent = null
  # resource_type - (required) is a type of string
  resource_type = null
  # vdc - (optional) is a type of string
  vdc = null
}
```

[top](#index)

### Variables

```terraform
variable "list_mode" {
  description = "(optional) - How the list should be built"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Unique name of the Info"
  type        = string
}

variable "name_id_separator" {
  description = "(optional) - Separator for name_id combination"
  type        = string
  default     = null
}

variable "org" {
  description = "(optional) - The name of organization to use, optional if defined at provider level. Useful when connected as sysadmin working across different organizations"
  type        = string
  default     = null
}

variable "parent" {
  description = "(optional) - The name of the parent to the resources being retrieved"
  type        = string
  default     = null
}

variable "resource_type" {
  description = "(required) - Which resource we should list"
  type        = string
}

variable "vdc" {
  description = "(optional) - The name of VDC to use, optional if defined at provider level"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "vcd_resource_list" "this" {
  # list_mode - (optional) is a type of string
  list_mode = var.list_mode
  # name - (required) is a type of string
  name = var.name
  # name_id_separator - (optional) is a type of string
  name_id_separator = var.name_id_separator
  # org - (optional) is a type of string
  org = var.org
  # parent - (optional) is a type of string
  parent = var.parent
  # resource_type - (required) is a type of string
  resource_type = var.resource_type
  # vdc - (optional) is a type of string
  vdc = var.vdc
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.vcd_resource_list.this.id
}

output "list" {
  description = "returns a list of string"
  value       = data.vcd_resource_list.this.list
}

output "this" {
  value = vcd_resource_list.this
}
```

[top](#index)