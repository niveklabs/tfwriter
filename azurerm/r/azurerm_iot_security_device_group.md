# azurerm_iot_security_device_group

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
module "azurerm_iot_security_device_group" {
  source = "./modules/azurerm/r/azurerm_iot_security_device_group"

  # iothub_id - (required) is a type of string
  iothub_id = null
  # name - (required) is a type of string
  name = null

  allow_rule = [{
    connection_to_ip_not_allowed = []
    local_user_not_allowed       = []
    process_not_allowed          = []
  }]

  range_rule = [{
    duration = null
    max      = null
    min      = null
    type     = null
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
variable "iothub_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "allow_rule" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      connection_to_ip_not_allowed = set(string)
      local_user_not_allowed       = set(string)
      process_not_allowed          = set(string)
    }
  ))
  default = []
}

variable "range_rule" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      duration = string
      max      = number
      min      = number
      type     = string
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
resource "azurerm_iot_security_device_group" "this" {
  # iothub_id - (required) is a type of string
  iothub_id = var.iothub_id
  # name - (required) is a type of string
  name = var.name

  dynamic "allow_rule" {
    for_each = var.allow_rule
    content {
      # connection_to_ip_not_allowed - (optional) is a type of set of string
      connection_to_ip_not_allowed = allow_rule.value["connection_to_ip_not_allowed"]
      # local_user_not_allowed - (optional) is a type of set of string
      local_user_not_allowed = allow_rule.value["local_user_not_allowed"]
      # process_not_allowed - (optional) is a type of set of string
      process_not_allowed = allow_rule.value["process_not_allowed"]
    }
  }

  dynamic "range_rule" {
    for_each = var.range_rule
    content {
      # duration - (required) is a type of string
      duration = range_rule.value["duration"]
      # max - (required) is a type of number
      max = range_rule.value["max"]
      # min - (required) is a type of number
      min = range_rule.value["min"]
      # type - (required) is a type of string
      type = range_rule.value["type"]
    }
  }

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
  value       = azurerm_iot_security_device_group.this.id
}

output "this" {
  value = azurerm_iot_security_device_group.this
}
```

[top](#index)