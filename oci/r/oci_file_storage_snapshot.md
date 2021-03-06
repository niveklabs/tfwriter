# oci_file_storage_snapshot

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
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_file_storage_snapshot" {
  source = "./modules/oci/r/oci_file_storage_snapshot"

  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # file_system_id - (required) is a type of string
  file_system_id = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # name - (required) is a type of string
  name = null

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
variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "file_system_id" {
  description = "(required)"
  type        = string
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
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
resource "oci_file_storage_snapshot" "this" {
  # defined_tags - (optional) is a type of map of string
  defined_tags = var.defined_tags
  # file_system_id - (required) is a type of string
  file_system_id = var.file_system_id
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = var.freeform_tags
  # name - (required) is a type of string
  name = var.name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
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
  value       = oci_file_storage_snapshot.this.defined_tags
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_file_storage_snapshot.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_file_storage_snapshot.this.id
}

output "is_clone_source" {
  description = "returns a bool"
  value       = oci_file_storage_snapshot.this.is_clone_source
}

output "lifecycle_details" {
  description = "returns a string"
  value       = oci_file_storage_snapshot.this.lifecycle_details
}

output "provenance_id" {
  description = "returns a string"
  value       = oci_file_storage_snapshot.this.provenance_id
}

output "state" {
  description = "returns a string"
  value       = oci_file_storage_snapshot.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_file_storage_snapshot.this.time_created
}

output "this" {
  value = oci_file_storage_snapshot.this
}
```

[top](#index)