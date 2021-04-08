# vcd_catalog

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
module "vcd_catalog" {
  source = "./modules/vcd/d/vcd_catalog"

  # description - (optional) is a type of string
  description = null
  # name - (optional) is a type of string
  name = null
  # org - (required) is a type of string
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
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - Name of the catalog. (Optional if 'filter' is used)"
  type        = string
  default     = null
}

variable "org" {
  description = "(required) - The name of organization to use, optional if defined at provider level. Useful when connected as sysadmin working across different organizations"
  type        = string
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
data "vcd_catalog" "this" {
  # description - (optional) is a type of string
  description = var.description
  # name - (optional) is a type of string
  name = var.name
  # org - (required) is a type of string
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
  value       = data.vcd_catalog.this.created
}

output "description" {
  description = "returns a string"
  value       = data.vcd_catalog.this.description
}

output "id" {
  description = "returns a string"
  value       = data.vcd_catalog.this.id
}

output "storage_profile_id" {
  description = "returns a string"
  value       = data.vcd_catalog.this.storage_profile_id
}

output "this" {
  value = vcd_catalog.this
}
```

[top](#index)