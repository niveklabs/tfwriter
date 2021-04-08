# vcd_independent_disk

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
module "vcd_independent_disk" {
  source = "./modules/vcd/r/vcd_independent_disk"

  # bus_sub_type - (optional) is a type of string
  bus_sub_type = null
  # bus_type - (optional) is a type of string
  bus_type = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # org - (optional) is a type of string
  org = null
  # size_in_mb - (required) is a type of number
  size_in_mb = null
  # storage_profile - (optional) is a type of string
  storage_profile = null
  # vdc - (optional) is a type of string
  vdc = null
}
```

[top](#index)

### Variables

```terraform
variable "bus_sub_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bus_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - independent disk description"
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

variable "size_in_mb" {
  description = "(required) - size in MB"
  type        = number
}

variable "storage_profile" {
  description = "(optional)"
  type        = string
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
resource "vcd_independent_disk" "this" {
  # bus_sub_type - (optional) is a type of string
  bus_sub_type = var.bus_sub_type
  # bus_type - (optional) is a type of string
  bus_type = var.bus_type
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # org - (optional) is a type of string
  org = var.org
  # size_in_mb - (required) is a type of number
  size_in_mb = var.size_in_mb
  # storage_profile - (optional) is a type of string
  storage_profile = var.storage_profile
  # vdc - (optional) is a type of string
  vdc = var.vdc
}
```

[top](#index)

### Outputs

```terraform
output "bus_sub_type" {
  description = "returns a string"
  value       = vcd_independent_disk.this.bus_sub_type
}

output "bus_type" {
  description = "returns a string"
  value       = vcd_independent_disk.this.bus_type
}

output "datastore_name" {
  description = "returns a string"
  value       = vcd_independent_disk.this.datastore_name
}

output "id" {
  description = "returns a string"
  value       = vcd_independent_disk.this.id
}

output "iops" {
  description = "returns a number"
  value       = vcd_independent_disk.this.iops
}

output "is_attached" {
  description = "returns a bool"
  value       = vcd_independent_disk.this.is_attached
}

output "owner_name" {
  description = "returns a string"
  value       = vcd_independent_disk.this.owner_name
}

output "storage_profile" {
  description = "returns a string"
  value       = vcd_independent_disk.this.storage_profile
}

output "this" {
  value = vcd_independent_disk.this
}
```

[top](#index)