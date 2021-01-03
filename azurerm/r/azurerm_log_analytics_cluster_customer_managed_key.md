# azurerm_log_analytics_cluster_customer_managed_key

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
module "azurerm_log_analytics_cluster_customer_managed_key" {
  source = "./modules/azurerm/r/azurerm_log_analytics_cluster_customer_managed_key"

  # key_vault_key_id - (required) is a type of string
  key_vault_key_id = null
  # log_analytics_cluster_id - (required) is a type of string
  log_analytics_cluster_id = null

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
variable "key_vault_key_id" {
  description = "(required)"
  type        = string
}

variable "log_analytics_cluster_id" {
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
resource "azurerm_log_analytics_cluster_customer_managed_key" "this" {
  key_vault_key_id         = var.key_vault_key_id
  log_analytics_cluster_id = var.log_analytics_cluster_id

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
  value       = azurerm_log_analytics_cluster_customer_managed_key.this.id
}

output "this" {
  value = azurerm_log_analytics_cluster_customer_managed_key.this
}
```

[top](#index)