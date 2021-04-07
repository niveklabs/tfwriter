# azurerm_dns_srv_record

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
module "azurerm_dns_srv_record" {
  source = "./modules/azurerm/r/azurerm_dns_srv_record"

  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # ttl - (required) is a type of number
  ttl = null
  # zone_name - (required) is a type of string
  zone_name = null

  record = [{
    port     = null
    priority = null
    target   = null
    weight   = null
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

variable "ttl" {
  description = "(required)"
  type        = number
}

variable "zone_name" {
  description = "(required)"
  type        = string
}

variable "record" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      port     = number
      priority = number
      target   = string
      weight   = number
    }
  ))
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
resource "azurerm_dns_srv_record" "this" {
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # tags - (optional) is a type of map of string
  tags = var.tags
  # ttl - (required) is a type of number
  ttl = var.ttl
  # zone_name - (required) is a type of string
  zone_name = var.zone_name

  dynamic "record" {
    for_each = var.record
    content {
      # port - (required) is a type of number
      port = record.value["port"]
      # priority - (required) is a type of number
      priority = record.value["priority"]
      # target - (required) is a type of string
      target = record.value["target"]
      # weight - (required) is a type of number
      weight = record.value["weight"]
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
output "fqdn" {
  description = "returns a string"
  value       = azurerm_dns_srv_record.this.fqdn
}

output "id" {
  description = "returns a string"
  value       = azurerm_dns_srv_record.this.id
}

output "this" {
  value = azurerm_dns_srv_record.this
}
```

[top](#index)