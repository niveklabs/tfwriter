# sumologic_folder

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
    sumologic = ">= 2.6.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "sumologic_folder" {
  source = "./modules/sumologic/r/sumologic_folder"

  # description - (required) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # parent_id - (required) is a type of string
  parent_id = null

  timeouts = [{
    delete = null
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
  description = "(required)"
  type        = string
}

variable "parent_id" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "sumologic_folder" "this" {
  description = var.description
  name        = var.name
  parent_id   = var.parent_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = sumologic_folder.this.id
}

output "this" {
  value = sumologic_folder.this
}
```

[top](#index)