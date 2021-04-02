# oci_datacatalog_connection

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
module "oci_datacatalog_connection" {
  source = "./modules/oci/r/oci_datacatalog_connection"

  # catalog_id - (required) is a type of string
  catalog_id = null
  # data_asset_key - (required) is a type of string
  data_asset_key = null
  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # enc_properties - (optional) is a type of map of string
  enc_properties = {}
  # is_default - (optional) is a type of bool
  is_default = null
  # properties - (required) is a type of map of string
  properties = {}
  # type_key - (required) is a type of string
  type_key = null

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
variable "catalog_id" {
  description = "(required)"
  type        = string
}

variable "data_asset_key" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(required)"
  type        = string
}

variable "enc_properties" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "is_default" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "properties" {
  description = "(required)"
  type        = map(string)
}

variable "type_key" {
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
resource "oci_datacatalog_connection" "this" {
  catalog_id     = var.catalog_id
  data_asset_key = var.data_asset_key
  description    = var.description
  display_name   = var.display_name
  enc_properties = var.enc_properties
  is_default     = var.is_default
  properties     = var.properties
  type_key       = var.type_key

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
output "created_by_id" {
  description = "returns a string"
  value       = oci_datacatalog_connection.this.created_by_id
}

output "description" {
  description = "returns a string"
  value       = oci_datacatalog_connection.this.description
}

output "external_key" {
  description = "returns a string"
  value       = oci_datacatalog_connection.this.external_key
}

output "id" {
  description = "returns a string"
  value       = oci_datacatalog_connection.this.id
}

output "is_default" {
  description = "returns a bool"
  value       = oci_datacatalog_connection.this.is_default
}

output "key" {
  description = "returns a string"
  value       = oci_datacatalog_connection.this.key
}

output "state" {
  description = "returns a string"
  value       = oci_datacatalog_connection.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_datacatalog_connection.this.time_created
}

output "time_status_updated" {
  description = "returns a string"
  value       = oci_datacatalog_connection.this.time_status_updated
}

output "time_updated" {
  description = "returns a string"
  value       = oci_datacatalog_connection.this.time_updated
}

output "updated_by_id" {
  description = "returns a string"
  value       = oci_datacatalog_connection.this.updated_by_id
}

output "uri" {
  description = "returns a string"
  value       = oci_datacatalog_connection.this.uri
}

output "this" {
  value = oci_datacatalog_connection.this
}
```

[top](#index)