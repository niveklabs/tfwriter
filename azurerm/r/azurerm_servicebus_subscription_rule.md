# azurerm_servicebus_subscription_rule

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
    azurerm = ">= 2.54.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_servicebus_subscription_rule" {
  source = "./modules/azurerm/r/azurerm_servicebus_subscription_rule"

  # action - (optional) is a type of string
  action = null
  # filter_type - (required) is a type of string
  filter_type = null
  # name - (required) is a type of string
  name = null
  # namespace_name - (required) is a type of string
  namespace_name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # sql_filter - (optional) is a type of string
  sql_filter = null
  # subscription_name - (required) is a type of string
  subscription_name = null
  # topic_name - (required) is a type of string
  topic_name = null

  correlation_filter = [{
    content_type        = null
    correlation_id      = null
    label               = null
    message_id          = null
    properties          = {}
    reply_to            = null
    reply_to_session_id = null
    session_id          = null
    to                  = null
  }]

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
variable "action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "filter_type" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "namespace_name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "sql_filter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subscription_name" {
  description = "(required)"
  type        = string
}

variable "topic_name" {
  description = "(required)"
  type        = string
}

variable "correlation_filter" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      content_type        = string
      correlation_id      = string
      label               = string
      message_id          = string
      properties          = map(string)
      reply_to            = string
      reply_to_session_id = string
      session_id          = string
      to                  = string
    }
  ))
  default = []
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
resource "azurerm_servicebus_subscription_rule" "this" {
  action              = var.action
  filter_type         = var.filter_type
  name                = var.name
  namespace_name      = var.namespace_name
  resource_group_name = var.resource_group_name
  sql_filter          = var.sql_filter
  subscription_name   = var.subscription_name
  topic_name          = var.topic_name

  dynamic "correlation_filter" {
    for_each = var.correlation_filter
    content {
      content_type        = correlation_filter.value["content_type"]
      correlation_id      = correlation_filter.value["correlation_id"]
      label               = correlation_filter.value["label"]
      message_id          = correlation_filter.value["message_id"]
      properties          = correlation_filter.value["properties"]
      reply_to            = correlation_filter.value["reply_to"]
      reply_to_session_id = correlation_filter.value["reply_to_session_id"]
      session_id          = correlation_filter.value["session_id"]
      to                  = correlation_filter.value["to"]
    }
  }

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
  value       = azurerm_servicebus_subscription_rule.this.id
}

output "this" {
  value = azurerm_servicebus_subscription_rule.this
}
```

[top](#index)