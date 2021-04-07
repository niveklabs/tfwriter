# prismacloud_alerts

[back](../prismacloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "prismacloud_alerts" {
  source = "./modules/prismacloud/d/prismacloud_alerts"

  # limit - (optional) is a type of number
  limit = null
  # sort_by - (optional) is a type of list of string
  sort_by = []

  filters = [{
    name     = null
    operator = null
    value    = null
  }]

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
  description = "(optional) - Max number of alerts to return.  This uses the v2 version of the API, where the default and max is 10,000."
  type        = number
  default     = null
}

variable "sort_by" {
  description = "(optional) - Array of sort properties. Append :asc or :desc to the key to sort by ascending or descending order respectively."
  type        = list(string)
  default     = null
}

variable "filters" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name     = string
      operator = string
      value    = string
    }
  ))
  default = []
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

### Datasource

```terraform
data "prismacloud_alerts" "this" {
  # limit - (optional) is a type of number
  limit = var.limit
  # sort_by - (optional) is a type of list of string
  sort_by = var.sort_by

  dynamic "filters" {
    for_each = var.filters
    content {
      # name - (required) is a type of string
      name = filters.value["name"]
      # operator - (optional) is a type of string
      operator = filters.value["operator"]
      # value - (required) is a type of string
      value = filters.value["value"]
    }
  }

  dynamic "time_range" {
    for_each = var.time_range
    content {

      dynamic "absolute" {
        for_each = time_range.value.absolute
        content {
          # end - (required) is a type of number
          end = absolute.value["end"]
          # start - (required) is a type of number
          start = absolute.value["start"]
        }
      }

      dynamic "relative" {
        for_each = time_range.value.relative
        content {
          # amount - (required) is a type of number
          amount = relative.value["amount"]
          # unit - (required) is a type of string
          unit = relative.value["unit"]
        }
      }

      dynamic "to_now" {
        for_each = time_range.value.to_now
        content {
          # unit - (required) is a type of string
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
  value       = data.prismacloud_alerts.this.id
}

output "listing" {
  description = "returns a list of object"
  value       = data.prismacloud_alerts.this.listing
}

output "page_token" {
  description = "returns a string"
  value       = data.prismacloud_alerts.this.page_token
}

output "total" {
  description = "returns a number"
  value       = data.prismacloud_alerts.this.total
}

output "this" {
  value = prismacloud_alerts.this
}
```

[top](#index)