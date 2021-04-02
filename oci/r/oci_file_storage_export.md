# oci_file_storage_export

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
    oci = ">= 4.20.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_file_storage_export" {
  source = "./modules/oci/r/oci_file_storage_export"

  # export_set_id - (required) is a type of string
  export_set_id = null
  # file_system_id - (required) is a type of string
  file_system_id = null
  # path - (required) is a type of string
  path = null

  export_options = [{
    access                         = null
    anonymous_gid                  = null
    anonymous_uid                  = null
    identity_squash                = null
    require_privileged_source_port = null
    source                         = null
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
variable "export_set_id" {
  description = "(required)"
  type        = string
}

variable "file_system_id" {
  description = "(required)"
  type        = string
}

variable "path" {
  description = "(required)"
  type        = string
}

variable "export_options" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      access                         = string
      anonymous_gid                  = string
      anonymous_uid                  = string
      identity_squash                = string
      require_privileged_source_port = bool
      source                         = string
    }
  ))
  default = []
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
resource "oci_file_storage_export" "this" {
  export_set_id  = var.export_set_id
  file_system_id = var.file_system_id
  path           = var.path

  dynamic "export_options" {
    for_each = var.export_options
    content {
      access                         = export_options.value["access"]
      anonymous_gid                  = export_options.value["anonymous_gid"]
      anonymous_uid                  = export_options.value["anonymous_uid"]
      identity_squash                = export_options.value["identity_squash"]
      require_privileged_source_port = export_options.value["require_privileged_source_port"]
      source                         = export_options.value["source"]
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
output "id" {
  description = "returns a string"
  value       = oci_file_storage_export.this.id
}

output "state" {
  description = "returns a string"
  value       = oci_file_storage_export.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_file_storage_export.this.time_created
}

output "this" {
  value = oci_file_storage_export.this
}
```

[top](#index)