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
  email    = var.email
  name     = var.name
  password = var.password

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create  = timeouts.value["create"]
      default = timeouts.value["default"]
      delete  = timeouts.value["delete"]
      update  = timeouts.value["update"]
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