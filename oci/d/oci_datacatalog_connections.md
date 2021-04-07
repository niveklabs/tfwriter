# oci_datacatalog_connections

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
module "oci_datacatalog_connections" {
  source = "./modules/oci/d/oci_datacatalog_connections"

  # catalog_id - (required) is a type of string
  catalog_id = null
  # created_by_id - (optional) is a type of string
  created_by_id = null
  # data_asset_key - (required) is a type of string
  data_asset_key = null
  # display_name - (optional) is a type of string
  display_name = null
  # display_name_contains - (optional) is a type of string
  display_name_contains = null
  # external_key - (optional) is a type of string
  external_key = null
  # fields - (optional) is a type of set of string
  fields = []
  # is_default - (optional) is a type of bool
  is_default = null
  # state - (optional) is a type of string
  state = null
  # time_created - (optional) is a type of string
  time_created = null
  # time_status_updated - (optional) is a type of string
  time_status_updated = null
  # time_updated - (optional) is a type of string
  time_updated = null
  # updated_by_id - (optional) is a type of string
  updated_by_id = null

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

variable "data_asset_key" {
  description = "(required)"
  type        = string
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

variable "is_default" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "time_created" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "time_status_updated" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "time_updated" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "updated_by_id" {
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
data "oci_datacatalog_connections" "this" {
  # catalog_id - (required) is a type of string
  catalog_id = var.catalog_id
  # created_by_id - (optional) is a type of string
  created_by_id = var.created_by_id
  # data_asset_key - (required) is a type of string
  data_asset_key = var.data_asset_key
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # display_name_contains - (optional) is a type of string
  display_name_contains = var.display_name_contains
  # external_key - (optional) is a type of string
  external_key = var.external_key
  # fields - (optional) is a type of set of string
  fields = var.fields
  # is_default - (optional) is a type of bool
  is_default = var.is_default
  # state - (optional) is a type of string
  state = var.state
  # time_created - (optional) is a type of string
  time_created = var.time_created
  # time_status_updated - (optional) is a type of string
  time_status_updated = var.time_status_updated
  # time_updated - (optional) is a type of string
  time_updated = var.time_updated
  # updated_by_id - (optional) is a type of string
  updated_by_id = var.updated_by_id

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
output "connection_collection" {
  description = "returns a list of object"
  value       = data.oci_datacatalog_connections.this.connection_collection
}

output "id" {
  description = "returns a string"
  value       = data.oci_datacatalog_connections.this.id
}

output "this" {
  value = oci_datacatalog_connections.this
}
```

[top](#index)