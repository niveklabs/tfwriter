# azurerm_security_center_contact

[back](../azurerm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azurerm = ">= 2.41.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_security_center_contact" {
  source = "./modules/azurerm/r/azurerm_security_center_contact"

  # alert_notifications - (required) is a type of bool
  alert_notifications = null
  # alerts_to_admins - (required) is a type of bool
  alerts_to_admins = null
  # email - (required) is a type of string
  email = null
  # phone - (optional) is a type of string
  phone = null

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "alert_notifications" {
  description = "(required)"
  type        = bool
}

variable "alerts_to_admins" {
  description = "(required)"
  type        = bool
}

variable "email" {
  description = "(required)"
  type        = string
}

variable "phone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      read   = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_security_center_contact" "this" {
  alert_notifications = var.alert_notifications
  alerts_to_admins    = var.alerts_to_admins
  email               = var.email
  phone               = var.phone

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
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
  value       = azurerm_security_center_contact.this.id
}

output "this" {
  value = azurerm_security_center_contact.this
}
```

[top](#index)