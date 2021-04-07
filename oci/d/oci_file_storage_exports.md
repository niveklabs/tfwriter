# oci_file_storage_exports

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
module "oci_file_storage_exports" {
  source = "./modules/oci/d/oci_file_storage_exports"

  # compartment_id - (optional) is a type of string
  compartment_id = null
  # export_set_id - (optional) is a type of string
  export_set_id = null
  # file_system_id - (optional) is a type of string
  file_system_id = null
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
variable "compartment_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "export_set_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "file_system_id" {
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
data "oci_file_storage_exports" "this" {
  compartment_id = var.compartment_id
  export_set_id  = var.export_set_id
  file_system_id = var.file_system_id
  state          = var.state

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
output "exports" {
  description = "returns a list of object"
  value       = data.oci_file_storage_exports.this.exports
}

output "id" {
  description = "returns a string"
  value       = data.oci_file_storage_exports.this.id
}

output "this" {
  value = oci_file_storage_exports.this
}
```

[top](#index)