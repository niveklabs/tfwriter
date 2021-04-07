# checkpoint_management_show_updatable_objects_repository_content

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
module "checkpoint_management_show_updatable_objects_repository_content" {
  source = "./modules/checkpoint/d/checkpoint_management_show_updatable_objects_repository_content"

  # filter - (optional) is a type of map of string
  filter = {}
  # limit - (optional) is a type of number
  limit = null
  # offset - (optional) is a type of number
  offset = null
  # uid_in_updatable_objects_repository - (optional) is a type of string
  uid_in_updatable_objects_repository = null

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
  description = "(optional) - Return results matching the specified filter."
  type        = map(string)
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

variable "uid_in_updatable_objects_repository" {
  description = "(optional) - The object's unique identifier in the Updatable Objects repository."
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
data "checkpoint_management_show_updatable_objects_repository_content" "this" {
  # filter - (optional) is a type of map of string
  filter = var.filter
  # limit - (optional) is a type of number
  limit = var.limit
  # offset - (optional) is a type of number
  offset = var.offset
  # uid_in_updatable_objects_repository - (optional) is a type of string
  uid_in_updatable_objects_repository = var.uid_in_updatable_objects_repository

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
  value       = data.checkpoint_management_show_updatable_objects_repository_content.this.from
}

output "id" {
  description = "returns a string"
  value       = data.checkpoint_management_show_updatable_objects_repository_content.this.id
}

output "objects" {
  description = "returns a list of object"
  value       = data.checkpoint_management_show_updatable_objects_repository_content.this.objects
}

output "to" {
  description = "returns a number"
  value       = data.checkpoint_management_show_updatable_objects_repository_content.this.to
}

output "total" {
  description = "returns a number"
  value       = data.checkpoint_management_show_updatable_objects_repository_content.this.total
}

output "this" {
  value = checkpoint_management_show_updatable_objects_repository_content.this
}
```

[top](#index)