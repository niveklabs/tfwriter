# azurerm_sql_failover_group

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
module "azurerm_sql_failover_group" {
  source = "./modules/azurerm/r/azurerm_sql_failover_group"

  # databases - (optional) is a type of set of string
  databases = []
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # server_name - (required) is a type of string
  server_name = null
  # tags - (optional) is a type of map of string
  tags = {}

  partner_servers = [{
    id       = null
    location = null
    role     = null
  }]

  read_write_endpoint_failover_policy = [{
    grace_minutes = null
    mode          = null
  }]

  readonly_endpoint_failover_policy = [{
    mode = null
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
variable "databases" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "server_name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "partner_servers" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      id       = string
      location = string
      role     = string
    }
  ))
}

variable "read_write_endpoint_failover_policy" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      grace_minutes = number
      mode          = string
    }
  ))
}

variable "readonly_endpoint_failover_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      mode = string
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
resource "azurerm_sql_failover_group" "this" {
  databases           = var.databases
  name                = var.name
  resource_group_name = var.resource_group_name
  server_name         = var.server_name
  tags                = var.tags

  dynamic "partner_servers" {
    for_each = var.partner_servers
    content {
      id = partner_servers.value["id"]
    }
  }

  dynamic "read_write_endpoint_failover_policy" {
    for_each = var.read_write_endpoint_failover_policy
    content {
      grace_minutes = read_write_endpoint_failover_policy.value["grace_minutes"]
      mode          = read_write_endpoint_failover_policy.value["mode"]
    }
  }

  dynamic "readonly_endpoint_failover_policy" {
    for_each = var.readonly_endpoint_failover_policy
    content {
      mode = readonly_endpoint_failover_policy.value["mode"]
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
  value       = azurerm_sql_failover_group.this.id
}

output "location" {
  description = "returns a string"
  value       = azurerm_sql_failover_group.this.location
}

output "role" {
  description = "returns a string"
  value       = azurerm_sql_failover_group.this.role
}

output "this" {
  value = azurerm_sql_failover_group.this
}
```

[top](#index)