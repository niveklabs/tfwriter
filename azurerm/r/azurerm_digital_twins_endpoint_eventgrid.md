# azurerm_digital_twins_endpoint_eventgrid

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
module "azurerm_digital_twins_endpoint_eventgrid" {
  source = "./modules/azurerm/r/azurerm_digital_twins_endpoint_eventgrid"

  # dead_letter_storage_secret - (optional) is a type of string
  dead_letter_storage_secret = null
  # digital_twins_id - (required) is a type of string
  digital_twins_id = null
  # eventgrid_topic_endpoint - (required) is a type of string
  eventgrid_topic_endpoint = null
  # eventgrid_topic_primary_access_key - (required) is a type of string
  eventgrid_topic_primary_access_key = null
  # eventgrid_topic_secondary_access_key - (required) is a type of string
  eventgrid_topic_secondary_access_key = null
  # name - (required) is a type of string
  name = null

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
variable "dead_letter_storage_secret" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "digital_twins_id" {
  description = "(required)"
  type        = string
}

variable "eventgrid_topic_endpoint" {
  description = "(required)"
  type        = string
}

variable "eventgrid_topic_primary_access_key" {
  description = "(required)"
  type        = string
}

variable "eventgrid_topic_secondary_access_key" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
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
resource "azurerm_digital_twins_endpoint_eventgrid" "this" {
  # dead_letter_storage_secret - (optional) is a type of string
  dead_letter_storage_secret = var.dead_letter_storage_secret
  # digital_twins_id - (required) is a type of string
  digital_twins_id = var.digital_twins_id
  # eventgrid_topic_endpoint - (required) is a type of string
  eventgrid_topic_endpoint = var.eventgrid_topic_endpoint
  # eventgrid_topic_primary_access_key - (required) is a type of string
  eventgrid_topic_primary_access_key = var.eventgrid_topic_primary_access_key
  # eventgrid_topic_secondary_access_key - (required) is a type of string
  eventgrid_topic_secondary_access_key = var.eventgrid_topic_secondary_access_key
  # name - (required) is a type of string
  name = var.name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # read - (optional) is a type of string
      read = timeouts.value["read"]
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
  value       = azurerm_digital_twins_endpoint_eventgrid.this.id
}

output "this" {
  value = azurerm_digital_twins_endpoint_eventgrid.this
}
```

[top](#index)