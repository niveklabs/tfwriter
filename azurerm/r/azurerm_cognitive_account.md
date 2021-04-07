# azurerm_cognitive_account

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
module "azurerm_cognitive_account" {
  source = "./modules/azurerm/r/azurerm_cognitive_account"

  # custom_subdomain_name - (optional) is a type of string
  custom_subdomain_name = null
  # kind - (required) is a type of string
  kind = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # qna_runtime_endpoint - (optional) is a type of string
  qna_runtime_endpoint = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # sku_name - (required) is a type of string
  sku_name = null
  # tags - (optional) is a type of map of string
  tags = {}

  network_acls = [{
    default_action             = null
    ip_rules                   = []
    virtual_network_subnet_ids = []
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
variable "custom_subdomain_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "kind" {
  description = "(required)"
  type        = string
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "qna_runtime_endpoint" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "sku_name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "network_acls" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      default_action             = string
      ip_rules                   = set(string)
      virtual_network_subnet_ids = set(string)
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
resource "azurerm_cognitive_account" "this" {
  # custom_subdomain_name - (optional) is a type of string
  custom_subdomain_name = var.custom_subdomain_name
  # kind - (required) is a type of string
  kind = var.kind
  # location - (required) is a type of string
  location = var.location
  # name - (required) is a type of string
  name = var.name
  # qna_runtime_endpoint - (optional) is a type of string
  qna_runtime_endpoint = var.qna_runtime_endpoint
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # sku_name - (required) is a type of string
  sku_name = var.sku_name
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "network_acls" {
    for_each = var.network_acls
    content {
      # default_action - (required) is a type of string
      default_action = network_acls.value["default_action"]
      # ip_rules - (optional) is a type of set of string
      ip_rules = network_acls.value["ip_rules"]
      # virtual_network_subnet_ids - (optional) is a type of set of string
      virtual_network_subnet_ids = network_acls.value["virtual_network_subnet_ids"]
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
output "endpoint" {
  description = "returns a string"
  value       = azurerm_cognitive_account.this.endpoint
}

output "id" {
  description = "returns a string"
  value       = azurerm_cognitive_account.this.id
}

output "primary_access_key" {
  description = "returns a string"
  value       = azurerm_cognitive_account.this.primary_access_key
  sensitive   = true
}

output "secondary_access_key" {
  description = "returns a string"
  value       = azurerm_cognitive_account.this.secondary_access_key
  sensitive   = true
}

output "this" {
  value = azurerm_cognitive_account.this
}
```

[top](#index)