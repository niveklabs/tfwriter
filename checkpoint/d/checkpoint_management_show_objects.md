# checkpoint_management_show_objects

[back](../checkpoint.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    checkpoint = ">= 1.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "checkpoint_management_show_objects" {
  source = "./modules/checkpoint/d/checkpoint_management_show_objects"

  # filter - (optional) is a type of string
  filter = null
  # ip_only - (optional) is a type of bool
  ip_only = null
  # limit - (optional) is a type of number
  limit = null
  # offset - (optional) is a type of number
  offset = null
  # type - (optional) is a type of string
  type = null

  order = [{
    asc  = null
    desc = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "filter" {
  description = "(optional) - Search expression to filter objects by. The provided text should be exactly the same as it would be given in Smart Console. The logical operators in the expression ('AND', 'OR') should be provided in capital letters. By default, the search involves both a textual search and a IP search. To use IP search only, set the \"ip-only\" parameter to true."
  type        = string
  default     = null
}

variable "ip_only" {
  description = "(optional) - If using \"filter\", use this field to search objects by their IP address only, without involving the textual search."
  type        = bool
  default     = null
}

variable "limit" {
  description = "(optional) - The maximal number of returned results."
  type        = number
  default     = null
}

variable "offset" {
  description = "(optional) - Number of the results to initially skip."
  type        = number
  default     = null
}

variable "type" {
  description = "(optional) - The objects' type, e.g.: host, service-tcp, network, address-range..."
  type        = string
  default     = null
}

variable "order" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      asc  = string
      desc = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "checkpoint_management_show_objects" "this" {
  # filter - (optional) is a type of string
  filter = var.filter
  # ip_only - (optional) is a type of bool
  ip_only = var.ip_only
  # limit - (optional) is a type of number
  limit = var.limit
  # offset - (optional) is a type of number
  offset = var.offset
  # type - (optional) is a type of string
  type = var.type

  dynamic "order" {
    for_each = var.order
    content {
      # asc - (optional) is a type of string
      asc = order.value["asc"]
      # desc - (optional) is a type of string
      desc = order.value["desc"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "from" {
  description = "returns a number"
  value       = data.checkpoint_management_show_objects.this.from
}

output "id" {
  description = "returns a string"
  value       = data.checkpoint_management_show_objects.this.id
}

output "objects" {
  description = "returns a list of object"
  value       = data.checkpoint_management_show_objects.this.objects
}

output "to" {
  description = "returns a number"
  value       = data.checkpoint_management_show_objects.this.to
}

output "total" {
  description = "returns a number"
  value       = data.checkpoint_management_show_objects.this.total
}

output "this" {
  value = checkpoint_management_show_objects.this
}
```

[top](#index)