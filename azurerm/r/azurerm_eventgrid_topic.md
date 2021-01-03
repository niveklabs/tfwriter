# azurerm_eventgrid_topic

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
module "azurerm_eventgrid_topic" {
  source = "./modules/azurerm/r/azurerm_eventgrid_topic"

  # input_schema - (optional) is a type of string
  input_schema = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}

  input_mapping_default_values = [{
    data_version = null
    event_type   = null
    subject      = null
  }]

  input_mapping_fields = [{
    data_version = null
    event_time   = null
    event_type   = null
    id           = null
    subject      = null
    topic        = null
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
variable "input_schema" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "input_mapping_default_values" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      data_version = string
      event_type   = string
      subject      = string
    }
  ))
  default = []
}

variable "input_mapping_fields" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      data_version = string
      event_time   = string
      event_type   = string
      id           = string
      subject      = string
      topic        = string
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
resource "azurerm_eventgrid_topic" "this" {
  input_schema        = var.input_schema
  location            = var.location
  name                = var.name
  resource_group_name = var.resource_group_name
  tags                = var.tags

  dynamic "input_mapping_default_values" {
    for_each = var.input_mapping_default_values
    content {
      data_version = input_mapping_default_values.value["data_version"]
      event_type   = input_mapping_default_values.value["event_type"]
      subject      = input_mapping_default_values.value["subject"]
    }
  }

  dynamic "input_mapping_fields" {
    for_each = var.input_mapping_fields
    content {
      data_version = input_mapping_fields.value["data_version"]
      event_time   = input_mapping_fields.value["event_time"]
      event_type   = input_mapping_fields.value["event_type"]
      id           = input_mapping_fields.value["id"]
      subject      = input_mapping_fields.value["subject"]
      topic        = input_mapping_fields.value["topic"]
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
output "endpoint" {
  description = "returns a string"
  value       = azurerm_eventgrid_topic.this.endpoint
}

output "id" {
  description = "returns a string"
  value       = azurerm_eventgrid_topic.this.id
}

output "primary_access_key" {
  description = "returns a string"
  value       = azurerm_eventgrid_topic.this.primary_access_key
  sensitive   = true
}

output "secondary_access_key" {
  description = "returns a string"
  value       = azurerm_eventgrid_topic.this.secondary_access_key
  sensitive   = true
}

output "this" {
  value = azurerm_eventgrid_topic.this
}
```

[top](#index)