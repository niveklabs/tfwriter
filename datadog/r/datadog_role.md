# datadog_role

[back](../datadog.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    datadog = ">= 2.24.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "datadog_role" {
  source = "./modules/datadog/r/datadog_role"

  # name - (required) is a type of string
  name = null

  permission = [{
    id   = null
    name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - Name of the role."
  type        = string
}

variable "permission" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      id   = string
      name = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "datadog_role" "this" {
  name = var.name

  dynamic "permission" {
    for_each = var.permission
    content {
      id = permission.value["id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = datadog_role.this.id
}

output "user_count" {
  description = "returns a number"
  value       = datadog_role.this.user_count
}

output "this" {
  value = datadog_role.this
}
```

[top](#index)