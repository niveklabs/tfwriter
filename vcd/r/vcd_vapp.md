# vcd_vapp

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
module "vcd_vapp" {
  source = "./modules/vcd/r/vcd_vapp"

  # description - (optional) is a type of string
  description = null
  # guest_properties - (optional) is a type of map of string
  guest_properties = {}
  # metadata - (optional) is a type of map of string
  metadata = {}
  # name - (required) is a type of string
  name = null
  # org - (optional) is a type of string
  org = null
  # power_on - (optional) is a type of bool
  power_on = null
  # vdc - (optional) is a type of string
  vdc = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Optional description of the vApp"
  type        = string
  default     = null
}

variable "guest_properties" {
  description = "(optional) - Key/value settings for guest properties. Will be picked up by new VMs when created."
  type        = map(string)
  default     = null
}

variable "metadata" {
  description = "(optional) - Key value map of metadata to assign to this vApp. Key and value can be any string."
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - A name for the vApp, unique withing the VDC"
  type        = string
}

variable "org" {
  description = "(optional) - The name of organization to use, optional if defined at provider level. Useful when connected as sysadmin working across different organizations"
  type        = string
  default     = null
}

variable "power_on" {
  description = "(optional) - A boolean value stating if this vApp should be powered on"
  type        = bool
  default     = null
}

variable "vdc" {
  description = "(optional) - The name of VDC to use, optional if defined at provider level"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vcd_vapp" "this" {
  # description - (optional) is a type of string
  description = var.description
  # guest_properties - (optional) is a type of map of string
  guest_properties = var.guest_properties
  # metadata - (optional) is a type of map of string
  metadata = var.metadata
  # name - (required) is a type of string
  name = var.name
  # org - (optional) is a type of string
  org = var.org
  # power_on - (optional) is a type of bool
  power_on = var.power_on
  # vdc - (optional) is a type of string
  vdc = var.vdc
}
```

[top](#index)

### Outputs

```terraform
output "href" {
  description = "returns a string"
  value       = vcd_vapp.this.href
}

output "id" {
  description = "returns a string"
  value       = vcd_vapp.this.id
}

output "status" {
  description = "returns a number"
  value       = vcd_vapp.this.status
}

output "status_text" {
  description = "returns a string"
  value       = vcd_vapp.this.status_text
}

output "this" {
  value = vcd_vapp.this
}
```

[top](#index)