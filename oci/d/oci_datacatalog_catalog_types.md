# oci_datacatalog_catalog_types

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
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_datacatalog_catalog_types" {
  source = "./modules/oci/d/oci_datacatalog_catalog_types"

  # catalog_id - (required) is a type of string
  catalog_id = null
  # external_type_name - (optional) is a type of string
  external_type_name = null
  # fields - (optional) is a type of set of string
  fields = []
  # is_approved - (optional) is a type of string
  is_approved = null
  # is_internal - (optional) is a type of string
  is_internal = null
  # is_tag - (optional) is a type of string
  is_tag = null
  # name - (optional) is a type of string
  name = null
  # state - (optional) is a type of string
  state = null
  # type_category - (optional) is a type of string
  type_category = null

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
variable "catalog_id" {
  description = "(required)"
  type        = string
}

variable "external_type_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fields" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "is_approved" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "is_internal" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "is_tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type_category" {
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
data "oci_datacatalog_catalog_types" "this" {
  catalog_id         = var.catalog_id
  external_type_name = var.external_type_name
  fields             = var.fields
  is_approved        = var.is_approved
  is_internal        = var.is_internal
  is_tag             = var.is_tag
  name               = var.name
  state              = var.state
  type_category      = var.type_category

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
  value       = data.oci_datacatalog_catalog_types.this.id
}

output "type_collection" {
  description = "returns a list of object"
  value       = data.oci_datacatalog_catalog_types.this.type_collection
}

output "this" {
  value = oci_datacatalog_catalog_types.this
}
```

[top](#index)