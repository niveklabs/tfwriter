# vsphere_host_pci_device

[back](../vsphere.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "vsphere_host_pci_device" {
  source = "./modules/vsphere/d/vsphere_host_pci_device"

  # class_id - (optional) is a type of string
  class_id = null
  # host_id - (required) is a type of string
  host_id = null
  # name_regex - (optional) is a type of string
  name_regex = null
  # vendor_id - (optional) is a type of string
  vendor_id = null
}
```

[top](#index)

### Variables

```terraform
variable "class_id" {
  description = "(optional) - The hexadecimal value of the PCI device's class ID."
  type        = string
  default     = null
}

variable "host_id" {
  description = "(required) - The Managed Object ID of the host system."
  type        = string
}

variable "name_regex" {
  description = "(optional) - A regular expression used to match the PCI device name."
  type        = string
  default     = null
}

variable "vendor_id" {
  description = "(optional) - The hexadecimal value of the PCI device's vendor ID."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "vsphere_host_pci_device" "this" {
  class_id   = var.class_id
  host_id    = var.host_id
  name_regex = var.name_regex
  vendor_id  = var.vendor_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.vsphere_host_pci_device.this.id
}

output "name" {
  description = "returns a string"
  value       = data.vsphere_host_pci_device.this.name
}

output "this" {
  value = vsphere_host_pci_device.this
}
```

[top](#index)