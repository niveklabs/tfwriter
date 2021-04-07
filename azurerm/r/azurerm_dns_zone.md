# azurerm_dns_zone

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
module "azurerm_dns_zone" {
  source = "./modules/azurerm/r/azurerm_dns_zone"

  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}

  soa_record = [{
    email         = null
    expire_time   = null
    fqdn          = null
    host_name     = null
    minimum_ttl   = null
    refresh_time  = null
    retry_time    = null
    serial_number = null
    tags          = {}
    ttl           = null
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

variable "soa_record" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      email         = string
      expire_time   = number
      fqdn          = string
      host_name     = string
      minimum_ttl   = number
      refresh_time  = number
      retry_time    = number
      serial_number = number
      tags          = map(string)
      ttl           = number
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
resource "azurerm_dns_zone" "this" {
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "soa_record" {
    for_each = var.soa_record
    content {
      # email - (required) is a type of string
      email = soa_record.value["email"]
      # expire_time - (optional) is a type of number
      expire_time = soa_record.value["expire_time"]
      # host_name - (required) is a type of string
      host_name = soa_record.value["host_name"]
      # minimum_ttl - (optional) is a type of number
      minimum_ttl = soa_record.value["minimum_ttl"]
      # refresh_time - (optional) is a type of number
      refresh_time = soa_record.value["refresh_time"]
      # retry_time - (optional) is a type of number
      retry_time = soa_record.value["retry_time"]
      # serial_number - (optional) is a type of number
      serial_number = soa_record.value["serial_number"]
      # tags - (optional) is a type of map of string
      tags = soa_record.value["tags"]
      # ttl - (optional) is a type of number
      ttl = soa_record.value["ttl"]
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
  value       = azurerm_dns_zone.this.id
}

output "max_number_of_record_sets" {
  description = "returns a number"
  value       = azurerm_dns_zone.this.max_number_of_record_sets
}

output "name_servers" {
  description = "returns a set of string"
  value       = azurerm_dns_zone.this.name_servers
}

output "number_of_record_sets" {
  description = "returns a number"
  value       = azurerm_dns_zone.this.number_of_record_sets
}

output "this" {
  value = azurerm_dns_zone.this
}
```

[top](#index)