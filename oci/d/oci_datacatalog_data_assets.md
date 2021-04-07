# oci_datacatalog_data_assets

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
module "oci_datacatalog_data_assets" {
  source = "./modules/oci/d/oci_datacatalog_data_assets"

  # catalog_id - (required) is a type of string
  catalog_id = null
  # created_by_id - (optional) is a type of string
  created_by_id = null
  # display_name - (optional) is a type of string
  display_name = null
  # display_name_contains - (optional) is a type of string
  display_name_contains = null
  # external_key - (optional) is a type of string
  external_key = null
  # fields - (optional) is a type of set of string
  fields = []
  # state - (optional) is a type of string
  state = null
  # type_key - (optional) is a type of string
  type_key = null

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

variable "created_by_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name_contains" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "external_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fields" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type_key" {
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
data "oci_datacatalog_data_assets" "this" {
  catalog_id            = var.catalog_id
  created_by_id         = var.created_by_id
  display_name          = var.display_name
  display_name_contains = var.display_name_contains
  external_key          = var.external_key
  fields                = var.fields
  state                 = var.state
  type_key              = var.type_key

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
output "data_asset_collection" {
  description = "returns a list of object"
  value       = data.oci_datacatalog_data_assets.this.data_asset_collection
}

output "id" {
  description = "returns a string"
  value       = data.oci_datacatalog_data_assets.this.id
}

output "this" {
  value = oci_datacatalog_data_assets.this
}
```

[top](#index)