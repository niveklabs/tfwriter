# ovh_me_installation_template_partition_scheme_partition

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
module "ovh_me_installation_template_partition_scheme_partition" {
  source = "./modules/ovh/r/ovh_me_installation_template_partition_scheme_partition"

  # filesystem - (required) is a type of string
  filesystem = null
  # mountpoint - (required) is a type of string
  mountpoint = null
  # order - (required) is a type of number
  order = null
  # raid - (optional) is a type of string
  raid = null
  # scheme_name - (required) is a type of string
  scheme_name = null
  # size - (required) is a type of number
  size = null
  # template_name - (required) is a type of string
  template_name = null
  # type - (required) is a type of string
  type = null
  # volume_name - (optional) is a type of string
  volume_name = null
}
```

[top](#index)

### Variables

```terraform
variable "filesystem" {
  description = "(required) - Partition filesystem"
  type        = string
}

variable "mountpoint" {
  description = "(required) - partition mount point"
  type        = string
}

variable "order" {
  description = "(required) - step or order. specifies the creation order of the partition on the disk"
  type        = number
}

variable "raid" {
  description = "(optional) - raid partition type"
  type        = string
  default     = null
}

variable "scheme_name" {
  description = "(required) - name of this partitioning scheme"
  type        = string
}

variable "size" {
  description = "(required) - size of partition in MB, 0 => rest of the space"
  type        = number
}

variable "template_name" {
  description = "(required) - Template name"
  type        = string
}

variable "type" {
  description = "(required) - partition type"
  type        = string
}

variable "volume_name" {
  description = "(optional) - The volume name needed for proxmox distribution"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "ovh_me_installation_template_partition_scheme_partition" "this" {
  filesystem    = var.filesystem
  mountpoint    = var.mountpoint
  order         = var.order
  raid          = var.raid
  scheme_name   = var.scheme_name
  size          = var.size
  template_name = var.template_name
  type          = var.type
  volume_name   = var.volume_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = ovh_me_installation_template_partition_scheme_partition.this.id
}

output "raid" {
  description = "returns a string"
  value       = ovh_me_installation_template_partition_scheme_partition.this.raid
}

output "volume_name" {
  description = "returns a string"
  value       = ovh_me_installation_template_partition_scheme_partition.this.volume_name
}

output "this" {
  value = ovh_me_installation_template_partition_scheme_partition.this
}
```

[top](#index)