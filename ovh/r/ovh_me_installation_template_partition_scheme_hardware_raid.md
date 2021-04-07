# ovh_me_installation_template_partition_scheme_hardware_raid

[back](../ovh.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ovh = ">= 0.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ovh_me_installation_template_partition_scheme_hardware_raid" {
  source = "./modules/ovh/r/ovh_me_installation_template_partition_scheme_hardware_raid"

  # disks - (required) is a type of list of string
  disks = []
  # mode - (required) is a type of string
  mode = null
  # name - (required) is a type of string
  name = null
  # scheme_name - (required) is a type of string
  scheme_name = null
  # step - (required) is a type of number
  step = null
  # template_name - (required) is a type of string
  template_name = null
}
```

[top](#index)

### Variables

```terraform
variable "disks" {
  description = "(required) - Disk List. Syntax is cX:dY for disks and [cX:dY,cX:dY] for groups. With X and Y resp. the controller id and the disk id"
  type        = list(string)
}

variable "mode" {
  description = "(required) - RAID mode (raid0, raid1, raid10, raid5, raid50, raid6, raid60)"
  type        = string
}

variable "name" {
  description = "(required) - Hardware RAID name"
  type        = string
}

variable "scheme_name" {
  description = "(required) - name of this partitioning scheme"
  type        = string
}

variable "step" {
  description = "(required) - Specifies the creation order of the hardware RAID"
  type        = number
}

variable "template_name" {
  description = "(required) - Template name"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "ovh_me_installation_template_partition_scheme_hardware_raid" "this" {
  # disks - (required) is a type of list of string
  disks = var.disks
  # mode - (required) is a type of string
  mode = var.mode
  # name - (required) is a type of string
  name = var.name
  # scheme_name - (required) is a type of string
  scheme_name = var.scheme_name
  # step - (required) is a type of number
  step = var.step
  # template_name - (required) is a type of string
  template_name = var.template_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = ovh_me_installation_template_partition_scheme_hardware_raid.this.id
}

output "this" {
  value = ovh_me_installation_template_partition_scheme_hardware_raid.this
}
```

[top](#index)