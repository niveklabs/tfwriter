# azurerm_application_insights_smart_detection_rule

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
    azurerm = ">= 2.53.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_application_insights_smart_detection_rule" {
  source = "./modules/azurerm/r/azurerm_application_insights_smart_detection_rule"

  # additional_email_recipients - (optional) is a type of set of string
  additional_email_recipients = []
  # application_insights_id - (required) is a type of string
  application_insights_id = null
  # enabled - (optional) is a type of bool
  enabled = null
  # name - (required) is a type of string
  name = null
  # send_emails_to_subscription_owners - (optional) is a type of bool
  send_emails_to_subscription_owners = null

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
variable "additional_email_recipients" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "application_insights_id" {
  description = "(required)"
  type        = string
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "send_emails_to_subscription_owners" {
  description = "(optional)"
  type        = bool
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
resource "azurerm_application_insights_smart_detection_rule" "this" {
  additional_email_recipients        = var.additional_email_recipients
  application_insights_id            = var.application_insights_id
  enabled                            = var.enabled
  name                               = var.name
  send_emails_to_subscription_owners = var.send_emails_to_subscription_owners

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
  value       = azurerm_application_insights_smart_detection_rule.this.id
}

output "this" {
  value = azurerm_application_insights_smart_detection_rule.this
}
```

[top](#index)