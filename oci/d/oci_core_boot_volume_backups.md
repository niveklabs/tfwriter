# oci_core_boot_volume_backups

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_core_boot_volume_backups" {
  source = "./modules/oci/d/oci_core_boot_volume_backups"

  # boot_volume_id - (optional) is a type of string
  boot_volume_id = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # display_name - (optional) is a type of string
  display_name = null
  # source_boot_volume_backup_id - (optional) is a type of string
  source_boot_volume_backup_id = null
  # state - (optional) is a type of string
  state = null

  filter = [{
    name   = null
    regex  = null
    values = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "boot_volume_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_boot_volume_backup_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "filter" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name   = string
      regex  = bool
      values = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "oci_core_boot_volume_backups" "this" {
  # boot_volume_id - (optional) is a type of string
  boot_volume_id = var.boot_volume_id
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # source_boot_volume_backup_id - (optional) is a type of string
  source_boot_volume_backup_id = var.source_boot_volume_backup_id
  # state - (optional) is a type of string
  state = var.state

  dynamic "filter" {
    for_each = var.filter
    content {
      # name - (required) is a type of string
      name = filter.value["name"]
      # regex - (optional) is a type of bool
      regex = filter.value["regex"]
      # values - (required) is a type of list of string
      values = filter.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "boot_volume_backups" {
  description = "returns a list of object"
  value       = data.oci_core_boot_volume_backups.this.boot_volume_backups
}

output "id" {
  description = "returns a string"
  value       = data.oci_core_boot_volume_backups.this.id
}

output "this" {
  value = oci_core_boot_volume_backups.this
}
```

[top](#index)