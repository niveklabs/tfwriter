# vcd_vm_internal_disk

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
module "vcd_vm_internal_disk" {
  source = "./modules/vcd/r/vcd_vm_internal_disk"

  # allow_vm_reboot - (optional) is a type of bool
  allow_vm_reboot = null
  # bus_number - (required) is a type of number
  bus_number = null
  # bus_type - (required) is a type of string
  bus_type = null
  # iops - (optional) is a type of number
  iops = null
  # org - (optional) is a type of string
  org = null
  # size_in_mb - (required) is a type of number
  size_in_mb = null
  # storage_profile - (optional) is a type of string
  storage_profile = null
  # unit_number - (required) is a type of number
  unit_number = null
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
variable "allow_vm_reboot" {
  description = "(optional) - Powers off VM when changing any attribute of an IDE disk or unit/bus number of other disk types, after the change is complete VM is powered back on. Without this setting enabled, such changes on a powered-on VM would fail."
  type        = bool
  default     = null
}

variable "bus_number" {
  description = "(required) - The number of the SCSI or IDE controller itself."
  type        = number
}

variable "bus_type" {
  description = "(required) - The type of disk controller. Possible values: ide, parallel( LSI Logic Parallel SCSI), sas(LSI Logic SAS (SCSI)), paravirtual(Paravirtual (SCSI)), sata"
  type        = string
}

variable "iops" {
  description = "(optional) - Specifies the IOPS for the disk."
  type        = number
  default     = null
}

variable "org" {
  description = "(optional) - The name of organization to use, optional if defined at provider level. Useful when connected as sysadmin working across different organizations"
  type        = string
  default     = null
}

variable "size_in_mb" {
  description = "(required) - The size of the disk in MB."
  type        = number
}

variable "storage_profile" {
  description = "(optional) - Storage profile to override the VM default one"
  type        = string
  default     = null
}

variable "unit_number" {
  description = "(required) - The device number on the SCSI or IDE controller of the disk."
  type        = number
}

variable "vapp_name" {
  description = "(required) - The vApp this VM internal disk belongs to"
  type        = string
}

variable "vdc" {
  description = "(optional) - The name of VDC to use, optional if defined at provider level"
  type        = string
  default     = null
}

variable "vm_name" {
  description = "(required) - VM in vApp in which internal disk is created"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "vcd_vm_internal_disk" "this" {
  # allow_vm_reboot - (optional) is a type of bool
  allow_vm_reboot = var.allow_vm_reboot
  # bus_number - (required) is a type of number
  bus_number = var.bus_number
  # bus_type - (required) is a type of string
  bus_type = var.bus_type
  # iops - (optional) is a type of number
  iops = var.iops
  # org - (optional) is a type of string
  org = var.org
  # size_in_mb - (required) is a type of number
  size_in_mb = var.size_in_mb
  # storage_profile - (optional) is a type of string
  storage_profile = var.storage_profile
  # unit_number - (required) is a type of number
  unit_number = var.unit_number
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
  value       = vcd_vm_internal_disk.this.id
}

output "iops" {
  description = "returns a number"
  value       = vcd_vm_internal_disk.this.iops
}

output "storage_profile" {
  description = "returns a string"
  value       = vcd_vm_internal_disk.this.storage_profile
}

output "thin_provisioned" {
  description = "returns a bool"
  value       = vcd_vm_internal_disk.this.thin_provisioned
}

output "this" {
  value = vcd_vm_internal_disk.this
}
```

[top](#index)