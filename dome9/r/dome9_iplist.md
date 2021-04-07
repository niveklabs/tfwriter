# dome9_iplist

[back](../dome9.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    dome9 = ">= 1.21.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "dome9_iplist" {
  source = "./modules/dome9/r/dome9_iplist"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null

  items = [{
    comment = null
    ip      = null
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
  description = "(required)"
  type        = string
}

variable "items" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      comment = string
      ip      = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "dome9_iplist" "this" {
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name

  dynamic "items" {
    for_each = var.items
    content {
      # comment - (optional) is a type of string
      comment = items.value["comment"]
      # ip - (optional) is a type of string
      ip = items.value["ip"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = dome9_iplist.this.description
}

output "id" {
  description = "returns a string"
  value       = dome9_iplist.this.id
}

output "this" {
  value = dome9_iplist.this
}
```

[top](#index)