# azurerm_healthcare_service

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
module "azurerm_healthcare_service" {
  source = "./modules/azurerm/r/azurerm_healthcare_service"

  # access_policy_object_ids - (optional) is a type of set of string
  access_policy_object_ids = []
  # cosmosdb_throughput - (optional) is a type of number
  cosmosdb_throughput = null
  # kind - (optional) is a type of string
  kind = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}

  authentication_configuration = [{
    audience            = null
    authority           = null
    smart_proxy_enabled = null
  }]

  cors_configuration = [{
    allow_credentials  = null
    allowed_headers    = []
    allowed_methods    = []
    allowed_origins    = []
    max_age_in_seconds = null
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
variable "access_policy_object_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "cosmosdb_throughput" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "kind" {
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

variable "authentication_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      audience            = string
      authority           = string
      smart_proxy_enabled = bool
    }
  ))
  default = []
}

variable "cors_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      allow_credentials  = bool
      allowed_headers    = set(string)
      allowed_methods    = list(string)
      allowed_origins    = set(string)
      max_age_in_seconds = number
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
resource "azurerm_healthcare_service" "this" {
  # access_policy_object_ids - (optional) is a type of set of string
  access_policy_object_ids = var.access_policy_object_ids
  # cosmosdb_throughput - (optional) is a type of number
  cosmosdb_throughput = var.cosmosdb_throughput
  # kind - (optional) is a type of string
  kind = var.kind
  # location - (required) is a type of string
  location = var.location
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "authentication_configuration" {
    for_each = var.authentication_configuration
    content {
      # audience - (optional) is a type of string
      audience = authentication_configuration.value["audience"]
      # authority - (optional) is a type of string
      authority = authentication_configuration.value["authority"]
      # smart_proxy_enabled - (optional) is a type of bool
      smart_proxy_enabled = authentication_configuration.value["smart_proxy_enabled"]
    }
  }

  dynamic "cors_configuration" {
    for_each = var.cors_configuration
    content {
      # allow_credentials - (optional) is a type of bool
      allow_credentials = cors_configuration.value["allow_credentials"]
      # allowed_headers - (optional) is a type of set of string
      allowed_headers = cors_configuration.value["allowed_headers"]
      # allowed_methods - (optional) is a type of list of string
      allowed_methods = cors_configuration.value["allowed_methods"]
      # allowed_origins - (optional) is a type of set of string
      allowed_origins = cors_configuration.value["allowed_origins"]
      # max_age_in_seconds - (optional) is a type of number
      max_age_in_seconds = cors_configuration.value["max_age_in_seconds"]
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
  value       = azurerm_healthcare_service.this.id
}

output "this" {
  value = azurerm_healthcare_service.this
}
```

[top](#index)