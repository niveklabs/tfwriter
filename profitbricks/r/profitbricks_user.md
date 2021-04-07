# profitbricks_user

[back](../profitbricks.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    profitbricks = ">= 1.6.5"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "profitbricks_user" {
  source = "./modules/profitbricks/r/profitbricks_user"

  # administrator - (required) is a type of bool
  administrator = null
  # email - (required) is a type of string
  email = null
  # first_name - (required) is a type of string
  first_name = null
  # force_sec_auth - (required) is a type of bool
  force_sec_auth = null
  # last_name - (required) is a type of string
  last_name = null
  # password - (required) is a type of string
  password = null

  timeouts = [{
    create  = null
    default = null
    delete  = null
    update  = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "administrator" {
  description = "(required)"
  type        = bool
}

variable "email" {
  description = "(required)"
  type        = string
}

variable "first_name" {
  description = "(required)"
  type        = string
}

variable "force_sec_auth" {
  description = "(required)"
  type        = bool
}

variable "last_name" {
  description = "(required)"
  type        = string
}

variable "password" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create  = string
      default = string
      delete  = string
      update  = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "profitbricks_user" "this" {
  # administrator - (required) is a type of bool
  administrator = var.administrator
  # email - (required) is a type of string
  email = var.email
  # first_name - (required) is a type of string
  first_name = var.first_name
  # force_sec_auth - (required) is a type of bool
  force_sec_auth = var.force_sec_auth
  # last_name - (required) is a type of string
  last_name = var.last_name
  # password - (required) is a type of string
  password = var.password

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # default - (optional) is a type of string
      default = timeouts.value["default"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = profitbricks_user.this.id
}

output "this" {
  value = profitbricks_user.this
}
```

[top](#index)