# vcd_independent_disk

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
module "vcd_independent_disk" {
  source = "./modules/vcd/d/vcd_independent_disk"

  # name - (optional) is a type of string
  name = null
  # org - (optional) is a type of string
  org = null
  # vdc - (optional) is a type of string
  vdc = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "org" {
  description = "(optional) - The name of organization to use, optional if defined at provider level. Useful when connected as sysadmin working across different organizations"
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

### Datasource

```terraform
data "vcd_independent_disk" "this" {
  # name - (optional) is a type of string
  name = var.name
  # org - (optional) is a type of string
  org = var.org
  # vdc - (optional) is a type of string
  vdc = var.vdc
}
```

[top](#index)

### Outputs

```terraform
output "bus_sub_type" {
  description = "returns a string"
  value       = data.vcd_independent_disk.this.bus_sub_type
}

output "bus_type" {
  description = "returns a string"
  value       = data.vcd_independent_disk.this.bus_type
}

output "datastore_name" {
  description = "returns a string"
  value       = data.vcd_independent_disk.this.datastore_name
}

output "description" {
  description = "returns a string"
  value       = data.vcd_independent_disk.this.description
}

output "id" {
  description = "returns a string"
  value       = data.vcd_independent_disk.this.id
}

output "iops" {
  description = "returns a number"
  value       = data.vcd_independent_disk.this.iops
}

output "is_attached" {
  description = "returns a bool"
  value       = data.vcd_independent_disk.this.is_attached
}

output "owner_name" {
  description = "returns a string"
  value       = data.vcd_independent_disk.this.owner_name
}

output "size_in_mb" {
  description = "returns a number"
  value       = data.vcd_independent_disk.this.size_in_mb
}

output "storage_profile" {
  description = "returns a string"
  value       = data.vcd_independent_disk.this.storage_profile
}

output "this" {
  value = vcd_independent_disk.this
}
```

[top](#index)