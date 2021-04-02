# oci_datacatalog_data_asset

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
module "oci_datacatalog_data_asset" {
  source = "./modules/oci/r/oci_datacatalog_data_asset"

  # catalog_id - (required) is a type of string
  catalog_id = null
  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # properties - (optional) is a type of map of string
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

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(required)"
  type        = string
}

variable "properties" {
  description = "(optional)"
  type        = map(string)
  default     = null
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
resource "oci_datacatalog_data_asset" "this" {
  catalog_id   = var.catalog_id
  description  = var.description
  display_name = var.display_name
  properties   = var.properties
  type_key     = var.type_key

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
  value       = oci_datacatalog_data_asset.this.created_by_id
}

output "description" {
  description = "returns a string"
  value       = oci_datacatalog_data_asset.this.description
}

output "external_key" {
  description = "returns a string"
  value       = oci_datacatalog_data_asset.this.external_key
}

output "id" {
  description = "returns a string"
  value       = oci_datacatalog_data_asset.this.id
}

output "key" {
  description = "returns a string"
  value       = oci_datacatalog_data_asset.this.key
}

output "properties" {
  description = "returns a map of string"
  value       = oci_datacatalog_data_asset.this.properties
}

output "state" {
  description = "returns a string"
  value       = oci_datacatalog_data_asset.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_datacatalog_data_asset.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = oci_datacatalog_data_asset.this.time_updated
}

output "updated_by_id" {
  description = "returns a string"
  value       = oci_datacatalog_data_asset.this.updated_by_id
}

output "uri" {
  description = "returns a string"
  value       = oci_datacatalog_data_asset.this.uri
}

output "this" {
  value = oci_datacatalog_data_asset.this
}
```

[top](#index)