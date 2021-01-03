# oci_core_volume_group

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_core_volume_group" {
  source = "./modules/oci/r/oci_core_volume_group"

  # availability_domain - (required) is a type of string
  availability_domain = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (optional) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}

  source_details = [{
    type                   = null
    volume_group_backup_id = null
    volume_group_id        = null
    volume_ids             = []
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "availability_domain" {
  description = "(required)"
  type        = string
}

variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "source_details" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      type                   = string
      volume_group_backup_id = string
      volume_group_id        = string
      volume_ids             = set(string)
    }
  ))
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "oci_core_volume_group" "this" {
  availability_domain = var.availability_domain
  compartment_id      = var.compartment_id
  defined_tags        = var.defined_tags
  display_name        = var.display_name
  freeform_tags       = var.freeform_tags

  dynamic "source_details" {
    for_each = var.source_details
    content {
      type                   = source_details.value["type"]
      volume_group_backup_id = source_details.value["volume_group_backup_id"]
      volume_group_id        = source_details.value["volume_group_id"]
      volume_ids             = source_details.value["volume_ids"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "defined_tags" {
  description = "returns a map of string"
  value       = oci_core_volume_group.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_core_volume_group.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_core_volume_group.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_core_volume_group.this.id
}

output "is_hydrated" {
  description = "returns a bool"
  value       = oci_core_volume_group.this.is_hydrated
}

output "size_in_gbs" {
  description = "returns a string"
  value       = oci_core_volume_group.this.size_in_gbs
}

output "size_in_mbs" {
  description = "returns a string"
  value       = oci_core_volume_group.this.size_in_mbs
}

output "state" {
  description = "returns a string"
  value       = oci_core_volume_group.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_core_volume_group.this.time_created
}

output "volume_ids" {
  description = "returns a list of string"
  value       = oci_core_volume_group.this.volume_ids
}

output "this" {
  value = oci_core_volume_group.this
}
```

[top](#index)