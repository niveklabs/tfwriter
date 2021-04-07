# profitbricks_backup_unit

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
module "profitbricks_backup_unit" {
  source = "./modules/profitbricks/r/profitbricks_backup_unit"

  # email - (required) is a type of string
  email = null
  # name - (required) is a type of string
  name = null
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
variable "email" {
  description = "(required) - The e-mail address you want assigned to the backup unit."
  type        = string
}

variable "name" {
  description = "(required) - Alphanumeric name you want assigned to the backup unit."
  type        = string
}

variable "password" {
  description = "(required) - The password you want assigned to the backup unit."
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
resource "profitbricks_backup_unit" "this" {
  # email - (required) is a type of string
  email = var.email
  # name - (required) is a type of string
  name = var.name
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
  value       = profitbricks_backup_unit.this.id
}

output "login" {
  description = "returns a string"
  value       = profitbricks_backup_unit.this.login
}

output "this" {
  value = profitbricks_backup_unit.this
}
```

[top](#index)