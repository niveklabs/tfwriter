# azurerm_stream_analytics_output_mssql

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
module "azurerm_stream_analytics_output_mssql" {
  source = "./modules/azurerm/r/azurerm_stream_analytics_output_mssql"

  # database - (required) is a type of string
  database = null
  # name - (required) is a type of string
  name = null
  # password - (required) is a type of string
  password = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # server - (required) is a type of string
  server = null
  # stream_analytics_job_name - (required) is a type of string
  stream_analytics_job_name = null
  # table - (required) is a type of string
  table = null
  # user - (required) is a type of string
  user = null

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
variable "database" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "password" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "server" {
  description = "(required)"
  type        = string
}

variable "stream_analytics_job_name" {
  description = "(required)"
  type        = string
}

variable "table" {
  description = "(required)"
  type        = string
}

variable "user" {
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
resource "azurerm_stream_analytics_output_mssql" "this" {
  database                  = var.database
  name                      = var.name
  password                  = var.password
  resource_group_name       = var.resource_group_name
  server                    = var.server
  stream_analytics_job_name = var.stream_analytics_job_name
  table                     = var.table
  user                      = var.user

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
  value       = azurerm_stream_analytics_output_mssql.this.id
}

output "this" {
  value = azurerm_stream_analytics_output_mssql.this
}
```

[top](#index)