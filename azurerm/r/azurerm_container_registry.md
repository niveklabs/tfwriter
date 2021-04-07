# azurerm_container_registry

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
module "azurerm_container_registry" {
  source = "./modules/azurerm/r/azurerm_container_registry"

  # admin_enabled - (optional) is a type of bool
  admin_enabled = null
  # georeplication_locations - (optional) is a type of set of string
  georeplication_locations = []
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # network_rule_set - (optional) is a type of list of object
  network_rule_set = [{
    default_action = null
    ip_rule = [{
      action   = null
      ip_range = null
    }]
    virtual_network = [{
      action    = null
      subnet_id = null
    }]
  }]
  # public_network_access_enabled - (optional) is a type of bool
  public_network_access_enabled = null
  # quarantine_policy_enabled - (optional) is a type of bool
  quarantine_policy_enabled = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # retention_policy - (optional) is a type of list of object
  retention_policy = [{
    days    = null
    enabled = null
  }]
  # sku - (optional) is a type of string
  sku = null
  # storage_account_id - (optional) is a type of string
  storage_account_id = null
  # tags - (optional) is a type of map of string
  tags = {}
  # trust_policy - (optional) is a type of list of object
  trust_policy = [{
    enabled = null
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
variable "admin_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "georeplication_locations" {
  description = "(optional)"
  type        = set(string)
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

variable "network_rule_set" {
  description = "(optional)"
  type = list(object(
    {
      default_action = string
      ip_rule = set(object(
        {
          action   = string
          ip_range = string
        }
      ))
      virtual_network = set(object(
        {
          action    = string
          subnet_id = string
        }
      ))
    }
  ))
  default = null
}

variable "public_network_access_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "quarantine_policy_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "retention_policy" {
  description = "(optional)"
  type = list(object(
    {
      days    = number
      enabled = bool
    }
  ))
  default = null
}

variable "sku" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "storage_account_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "trust_policy" {
  description = "(optional)"
  type = list(object(
    {
      enabled = bool
    }
  ))
  default = null
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
resource "azurerm_container_registry" "this" {
  # admin_enabled - (optional) is a type of bool
  admin_enabled = var.admin_enabled
  # georeplication_locations - (optional) is a type of set of string
  georeplication_locations = var.georeplication_locations
  # location - (required) is a type of string
  location = var.location
  # name - (required) is a type of string
  name = var.name
  # network_rule_set - (optional) is a type of list of object
  network_rule_set = var.network_rule_set
  # public_network_access_enabled - (optional) is a type of bool
  public_network_access_enabled = var.public_network_access_enabled
  # quarantine_policy_enabled - (optional) is a type of bool
  quarantine_policy_enabled = var.quarantine_policy_enabled
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # retention_policy - (optional) is a type of list of object
  retention_policy = var.retention_policy
  # sku - (optional) is a type of string
  sku = var.sku
  # storage_account_id - (optional) is a type of string
  storage_account_id = var.storage_account_id
  # tags - (optional) is a type of map of string
  tags = var.tags
  # trust_policy - (optional) is a type of list of object
  trust_policy = var.trust_policy

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
output "admin_password" {
  description = "returns a string"
  value       = azurerm_container_registry.this.admin_password
  sensitive   = true
}

output "admin_username" {
  description = "returns a string"
  value       = azurerm_container_registry.this.admin_username
}

output "id" {
  description = "returns a string"
  value       = azurerm_container_registry.this.id
}

output "login_server" {
  description = "returns a string"
  value       = azurerm_container_registry.this.login_server
}

output "network_rule_set" {
  description = "returns a list of object"
  value       = azurerm_container_registry.this.network_rule_set
}

output "retention_policy" {
  description = "returns a list of object"
  value       = azurerm_container_registry.this.retention_policy
}

output "trust_policy" {
  description = "returns a list of object"
  value       = azurerm_container_registry.this.trust_policy
}

output "this" {
  value = azurerm_container_registry.this
}
```

[top](#index)