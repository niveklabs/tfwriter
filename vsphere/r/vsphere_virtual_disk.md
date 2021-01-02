# vsphere_virtual_disk

[back](../vsphere.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vsphere = ">= 1.24.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vsphere_virtual_disk" {
  source = "./modules/vsphere/r/vsphere_virtual_disk"

  # adapter_type - (optional) is a type of string
  adapter_type = null
  # create_directories - (optional) is a type of bool
  create_directories = null
  # datacenter - (optional) is a type of string
  datacenter = null
  # datastore - (required) is a type of string
  datastore = null
  # size - (required) is a type of number
  size = null
  # type - (optional) is a type of string
  type = null
  # vmdk_path - (required) is a type of string
  vmdk_path = null
}
```

[top](#index)

### Variables

```terraform
variable "adapter_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "create_directories" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "datacenter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "datastore" {
  description = "(required)"
  type        = string
}

variable "size" {
  description = "(required)"
  type        = number
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vmdk_path" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "vsphere_virtual_disk" "this" {
  adapter_type       = var.adapter_type
  create_directories = var.create_directories
  datacenter         = var.datacenter
  datastore          = var.datastore
  size               = var.size
  type               = var.type
  vmdk_path          = var.vmdk_path
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vsphere_virtual_disk.this.id
}

output "this" {
  value = vsphere_virtual_disk.this
}
```

[top](#index)