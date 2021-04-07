# panos_panorama_device_group_entry

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    panos = ">= 1.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_panorama_device_group_entry" {
  source = "./modules/panos/r/panos_panorama_device_group_entry"

  # device_group - (required) is a type of string
  device_group = null
  # serial - (required) is a type of string
  serial = null
  # vsys_list - (optional) is a type of set of string
  vsys_list = []
}
```

[top](#index)

### Variables

```terraform
variable "device_group" {
  description = "(required)"
  type        = string
}

variable "serial" {
  description = "(required)"
  type        = string
}

variable "vsys_list" {
  description = "(optional)"
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "panos_panorama_device_group_entry" "this" {
  # device_group - (required) is a type of string
  device_group = var.device_group
  # serial - (required) is a type of string
  serial = var.serial
  # vsys_list - (optional) is a type of set of string
  vsys_list = var.vsys_list
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_panorama_device_group_entry.this.id
}

output "this" {
  value = panos_panorama_device_group_entry.this
}
```

[top](#index)