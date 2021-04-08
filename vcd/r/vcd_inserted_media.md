# vcd_inserted_media

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
module "vcd_inserted_media" {
  source = "./modules/vcd/r/vcd_inserted_media"

  # catalog - (required) is a type of string
  catalog = null
  # eject_force - (optional) is a type of bool
  eject_force = null
  # name - (required) is a type of string
  name = null
  # org - (optional) is a type of string
  org = null
  # vapp_name - (required) is a type of string
  vapp_name = null
  # vdc - (optional) is a type of string
  vdc = null
  # vm_name - (required) is a type of string
  vm_name = null
}
```

[top](#index)

### Variables

```terraform
variable "catalog" {
  description = "(required) - catalog name where to find media file"
  type        = string
}

variable "eject_force" {
  description = "(optional) - When ejecting answers automatically to question yes"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - media name to use"
  type        = string
}

variable "org" {
  description = "(optional) - The name of organization to use, optional if defined at provider level. Useful when connected as sysadmin working across different organizations"
  type        = string
  default     = null
}

variable "vapp_name" {
  description = "(required) - vApp to use"
  type        = string
}

variable "vdc" {
  description = "(optional) - The name of VDC to use, optional if defined at provider level"
  type        = string
  default     = null
}

variable "vm_name" {
  description = "(required) - VM in vApp in which media will be inserted or ejected"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "vcd_inserted_media" "this" {
  # catalog - (required) is a type of string
  catalog = var.catalog
  # eject_force - (optional) is a type of bool
  eject_force = var.eject_force
  # name - (required) is a type of string
  name = var.name
  # org - (optional) is a type of string
  org = var.org
  # vapp_name - (required) is a type of string
  vapp_name = var.vapp_name
  # vdc - (optional) is a type of string
  vdc = var.vdc
  # vm_name - (required) is a type of string
  vm_name = var.vm_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vcd_inserted_media.this.id
}

output "this" {
  value = vcd_inserted_media.this
}
```

[top](#index)