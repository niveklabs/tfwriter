# vcd_catalog_item

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
module "vcd_catalog_item" {
  source = "./modules/vcd/d/vcd_catalog_item"

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
  description = "(required) - catalog containing the item"
  type        = string
}

variable "name" {
  description = "(optional) - Name of the item. It is optional when a filter is provided"
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
data "vcd_catalog_item" "this" {
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
output "created" {
  description = "returns a string"
  value       = data.vcd_catalog_item.this.created
}

output "description" {
  description = "returns a string"
  value       = data.vcd_catalog_item.this.description
}

output "id" {
  description = "returns a string"
  value       = data.vcd_catalog_item.this.id
}

output "metadata" {
  description = "returns a map of string"
  value       = data.vcd_catalog_item.this.metadata
}

output "this" {
  value = vcd_catalog_item.this
}
```

[top](#index)