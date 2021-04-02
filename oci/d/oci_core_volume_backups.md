# oci_core_volume_backups

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
    oci = ">= 4.20.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_core_volume_backups" {
  source = "./modules/oci/d/oci_core_volume_backups"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # display_name - (optional) is a type of string
  display_name = null
  # source_volume_backup_id - (optional) is a type of string
  source_volume_backup_id = null
  # state - (optional) is a type of string
  state = null
  # volume_id - (optional) is a type of string
  volume_id = null

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
variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_volume_backup_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "volume_id" {
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
data "oci_core_volume_backups" "this" {
  compartment_id          = var.compartment_id
  display_name            = var.display_name
  source_volume_backup_id = var.source_volume_backup_id
  state                   = var.state
  volume_id               = var.volume_id

  dynamic "filter" {
    for_each = var.filter
    content {
      name   = filter.value["name"]
      regex  = filter.value["regex"]
      values = filter.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.oci_core_volume_backups.this.id
}

output "volume_backups" {
  description = "returns a list of object"
  value       = data.oci_core_volume_backups.this.volume_backups
}

output "this" {
  value = oci_core_volume_backups.this
}
```

[top](#index)