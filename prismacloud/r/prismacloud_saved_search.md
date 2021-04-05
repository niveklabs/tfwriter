# prismacloud_saved_search

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
module "prismacloud_saved_search" {
  source = "./modules/prismacloud/r/prismacloud_saved_search"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # query - (required) is a type of string
  query = null
  # search_id - (required) is a type of string
  search_id = null

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
variable "description" {
  description = "(optional) - Description"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Saved search name"
  type        = string
}

variable "query" {
  description = "(required) - The RQL search to perform"
  type        = string
}

variable "search_id" {
  description = "(required) - The RQL UUID"
  type        = string
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
resource "prismacloud_saved_search" "this" {
  description = var.description
  name        = var.name
  query       = var.query
  search_id   = var.search_id

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
output "id" {
  description = "returns a string"
  value       = prismacloud_saved_search.this.id
}

output "saved" {
  description = "returns a bool"
  value       = prismacloud_saved_search.this.saved
}

output "this" {
  value = prismacloud_saved_search.this
}
```

[top](#index)