# vcd_catalog_media

[back](../vcd.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vcd = ">= 3.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vcd_catalog_media" {
  source = "./modules/vcd/d/vcd_catalog_media"

  # catalog - (required) is a type of string
  catalog = null
  # name - (optional) is a type of string
  name = null
  # org - (optional) is a type of string
  org = null

  filter = [{
    date     = null
    earliest = null
    latest   = null
    metadata = [{
      is_system      = null
      key            = null
      type           = null
      use_api_search = null
      value          = null
    }]
    name_regex = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "catalog" {
  description = "(required) - catalog name where upload the Media file"
  type        = string
}

variable "name" {
  description = "(optional) - media name (Optional when 'filter' is used)"
  type        = string
  default     = null
}

variable "org" {
  description = "(optional) - The name of organization to use, optional if defined at provider level. Useful when connected as sysadmin working across different organizations"
  type        = string
  default     = null
}

variable "filter" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      date     = string
      earliest = bool
      latest   = bool
      metadata = list(object(
        {
          is_system      = bool
          key            = string
          type           = string
          use_api_search = bool
          value          = string
        }
      ))
      name_regex = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "vcd_catalog_media" "this" {
  # catalog - (required) is a type of string
  catalog = var.catalog
  # name - (optional) is a type of string
  name = var.name
  # org - (optional) is a type of string
  org = var.org

  dynamic "filter" {
    for_each = var.filter
    content {
      # date - (optional) is a type of string
      date = filter.value["date"]
      # earliest - (optional) is a type of bool
      earliest = filter.value["earliest"]
      # latest - (optional) is a type of bool
      latest = filter.value["latest"]
      # name_regex - (optional) is a type of string
      name_regex = filter.value["name_regex"]

      dynamic "metadata" {
        for_each = filter.value.metadata
        content {
          # is_system - (optional) is a type of bool
          is_system = metadata.value["is_system"]
          # key - (required) is a type of string
          key = metadata.value["key"]
          # type - (optional) is a type of string
          type = metadata.value["type"]
          # use_api_search - (optional) is a type of bool
          use_api_search = metadata.value["use_api_search"]
          # value - (required) is a type of string
          value = metadata.value["value"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "creation_date" {
  description = "returns a string"
  value       = data.vcd_catalog_media.this.creation_date
}

output "description" {
  description = "returns a string"
  value       = data.vcd_catalog_media.this.description
}

output "id" {
  description = "returns a string"
  value       = data.vcd_catalog_media.this.id
}

output "is_iso" {
  description = "returns a bool"
  value       = data.vcd_catalog_media.this.is_iso
}

output "is_published" {
  description = "returns a bool"
  value       = data.vcd_catalog_media.this.is_published
}

output "metadata" {
  description = "returns a map of string"
  value       = data.vcd_catalog_media.this.metadata
}

output "owner_name" {
  description = "returns a string"
  value       = data.vcd_catalog_media.this.owner_name
}

output "size" {
  description = "returns a number"
  value       = data.vcd_catalog_media.this.size
}

output "status" {
  description = "returns a string"
  value       = data.vcd_catalog_media.this.status
}

output "storage_profile_name" {
  description = "returns a string"
  value       = data.vcd_catalog_media.this.storage_profile_name
}

output "this" {
  value = vcd_catalog_media.this
}
```

[top](#index)