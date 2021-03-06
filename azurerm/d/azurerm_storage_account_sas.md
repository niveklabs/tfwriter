# azurerm_storage_account_sas

[back](../azurerm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "azurerm_storage_account_sas" {
  source = "./modules/azurerm/d/azurerm_storage_account_sas"

  # connection_string - (required) is a type of string
  connection_string = null
  # expiry - (required) is a type of string
  expiry = null
  # https_only - (optional) is a type of bool
  https_only = null
  # signed_version - (optional) is a type of string
  signed_version = null
  # start - (required) is a type of string
  start = null

  permissions = [{
    add     = null
    create  = null
    delete  = null
    list    = null
    process = null
    read    = null
    update  = null
    write   = null
  }]

  resource_types = [{
    container = null
    object    = null
    service   = null
  }]

  services = [{
    blob  = null
    file  = null
    queue = null
    table = null
  }]

  timeouts = [{
    read = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "connection_string" {
  description = "(required)"
  type        = string
}

variable "expiry" {
  description = "(required)"
  type        = string
}

variable "https_only" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "signed_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "start" {
  description = "(required)"
  type        = string
}

variable "permissions" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      add     = bool
      create  = bool
      delete  = bool
      list    = bool
      process = bool
      read    = bool
      update  = bool
      write   = bool
    }
  ))
}

variable "resource_types" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      container = bool
      object    = bool
      service   = bool
    }
  ))
}

variable "services" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      blob  = bool
      file  = bool
      queue = bool
      table = bool
    }
  ))
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      read = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "azurerm_storage_account_sas" "this" {
  # connection_string - (required) is a type of string
  connection_string = var.connection_string
  # expiry - (required) is a type of string
  expiry = var.expiry
  # https_only - (optional) is a type of bool
  https_only = var.https_only
  # signed_version - (optional) is a type of string
  signed_version = var.signed_version
  # start - (required) is a type of string
  start = var.start

  dynamic "permissions" {
    for_each = var.permissions
    content {
      # add - (required) is a type of bool
      add = permissions.value["add"]
      # create - (required) is a type of bool
      create = permissions.value["create"]
      # delete - (required) is a type of bool
      delete = permissions.value["delete"]
      # list - (required) is a type of bool
      list = permissions.value["list"]
      # process - (required) is a type of bool
      process = permissions.value["process"]
      # read - (required) is a type of bool
      read = permissions.value["read"]
      # update - (required) is a type of bool
      update = permissions.value["update"]
      # write - (required) is a type of bool
      write = permissions.value["write"]
    }
  }

  dynamic "resource_types" {
    for_each = var.resource_types
    content {
      # container - (required) is a type of bool
      container = resource_types.value["container"]
      # object - (required) is a type of bool
      object = resource_types.value["object"]
      # service - (required) is a type of bool
      service = resource_types.value["service"]
    }
  }

  dynamic "services" {
    for_each = var.services
    content {
      # blob - (required) is a type of bool
      blob = services.value["blob"]
      # file - (required) is a type of bool
      file = services.value["file"]
      # queue - (required) is a type of bool
      queue = services.value["queue"]
      # table - (required) is a type of bool
      table = services.value["table"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # read - (optional) is a type of string
      read = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.azurerm_storage_account_sas.this.id
}

output "sas" {
  description = "returns a string"
  value       = data.azurerm_storage_account_sas.this.sas
  sensitive   = true
}

output "this" {
  value = azurerm_storage_account_sas.this
}
```

[top](#index)