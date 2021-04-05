# prismacloud_rql_search

[back](../prismacloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    prismacloud = ">= 1.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "prismacloud_rql_search" {
  source = "./modules/prismacloud/r/prismacloud_rql_search"

  # limit - (optional) is a type of number
  limit = null
  # query - (required) is a type of string
  query = null
  # search_type - (optional) is a type of string
  search_type = null

  time_range = [{
    absolute = [{
      end   = null
      start = null
    }]
    relative = [{
      amount = null
      unit   = null
    }]
    to_now = [{
      unit = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "limit" {
  description = "(optional) - Limit results"
  type        = number
  default     = null
}

variable "query" {
  description = "(required) - The RQL search to perform"
  type        = string
}

variable "search_type" {
  description = "(optional) - The search type"
  type        = string
  default     = null
}

variable "time_range" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      absolute = list(object(
        {
          end   = number
          start = number
        }
      ))
      relative = list(object(
        {
          amount = number
          unit   = string
        }
      ))
      to_now = list(object(
        {
          unit = string
        }
      ))
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "prismacloud_rql_search" "this" {
  limit       = var.limit
  query       = var.query
  search_type = var.search_type

  dynamic "time_range" {
    for_each = var.time_range
    content {

      dynamic "absolute" {
        for_each = time_range.value.absolute
        content {
          end   = absolute.value["end"]
          start = absolute.value["start"]
        }
      }

      dynamic "relative" {
        for_each = time_range.value.relative
        content {
          amount = relative.value["amount"]
          unit   = relative.value["unit"]
        }
      }

      dynamic "to_now" {
        for_each = time_range.value.to_now
        content {
          unit = to_now.value["unit"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cloud_type" {
  description = "returns a string"
  value       = prismacloud_rql_search.this.cloud_type
}

output "config_data" {
  description = "returns a list of object"
  value       = prismacloud_rql_search.this.config_data
}

output "description" {
  description = "returns a string"
  value       = prismacloud_rql_search.this.description
}

output "event_data" {
  description = "returns a list of object"
  value       = prismacloud_rql_search.this.event_data
}

output "group_by" {
  description = "returns a list of string"
  value       = prismacloud_rql_search.this.group_by
}

output "id" {
  description = "returns a string"
  value       = prismacloud_rql_search.this.id
}

output "name" {
  description = "returns a string"
  value       = prismacloud_rql_search.this.name
}

output "search_id" {
  description = "returns a string"
  value       = prismacloud_rql_search.this.search_id
}

output "this" {
  value = prismacloud_rql_search.this
}
```

[top](#index)