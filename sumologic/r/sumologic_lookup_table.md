# sumologic_lookup_table

[back](../sumologic.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    sumologic = ">= 2.9.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "sumologic_lookup_table" {
  source = "./modules/sumologic/r/sumologic_lookup_table"

  # description - (required) is a type of string
  description = null
  # name - (optional) is a type of string
  name = null
  # parent_folder_id - (optional) is a type of string
  parent_folder_id = null
  # primary_keys - (optional) is a type of list of string
  primary_keys = []
  # size_limit_action - (optional) is a type of string
  size_limit_action = null
  # ttl - (optional) is a type of number
  ttl = null

  fields = [{
    field_name = null
    field_type = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "parent_folder_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "primary_keys" {
  description = "(optional) - The primary key field names."
  type        = list(string)
  default     = null
}

variable "size_limit_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "fields" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      field_name = string
      field_type = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "sumologic_lookup_table" "this" {
  # description - (required) is a type of string
  description = var.description
  # name - (optional) is a type of string
  name = var.name
  # parent_folder_id - (optional) is a type of string
  parent_folder_id = var.parent_folder_id
  # primary_keys - (optional) is a type of list of string
  primary_keys = var.primary_keys
  # size_limit_action - (optional) is a type of string
  size_limit_action = var.size_limit_action
  # ttl - (optional) is a type of number
  ttl = var.ttl

  dynamic "fields" {
    for_each = var.fields
    content {
      # field_name - (required) is a type of string
      field_name = fields.value["field_name"]
      # field_type - (required) is a type of string
      field_type = fields.value["field_type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = sumologic_lookup_table.this.id
}

output "this" {
  value = sumologic_lookup_table.this
}
```

[top](#index)