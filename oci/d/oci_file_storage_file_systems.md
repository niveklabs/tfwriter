# oci_file_storage_file_systems

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
module "oci_file_storage_file_systems" {
  source = "./modules/oci/d/oci_file_storage_file_systems"

  # availability_domain - (required) is a type of string
  availability_domain = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # display_name - (optional) is a type of string
  display_name = null
  # parent_file_system_id - (optional) is a type of string
  parent_file_system_id = null
  # source_snapshot_id - (optional) is a type of string
  source_snapshot_id = null
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
variable "availability_domain" {
  description = "(required)"
  type        = string
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

variable "parent_file_system_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_snapshot_id" {
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
data "oci_file_storage_file_systems" "this" {
  availability_domain   = var.availability_domain
  compartment_id        = var.compartment_id
  display_name          = var.display_name
  parent_file_system_id = var.parent_file_system_id
  source_snapshot_id    = var.source_snapshot_id
  state                 = var.state

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
output "file_systems" {
  description = "returns a list of object"
  value       = data.oci_file_storage_file_systems.this.file_systems
}

output "id" {
  description = "returns a string"
  value       = data.oci_file_storage_file_systems.this.id
}

output "this" {
  value = oci_file_storage_file_systems.this
}
```

[top](#index)