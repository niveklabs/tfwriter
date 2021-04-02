# azurerm_kusto_cluster_customer_managed_key

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
module "azurerm_kusto_cluster_customer_managed_key" {
  source = "./modules/azurerm/r/azurerm_kusto_cluster_customer_managed_key"

  # cluster_id - (required) is a type of string
  cluster_id = null
  # key_name - (required) is a type of string
  key_name = null
  # key_vault_id - (required) is a type of string
  key_vault_id = null
  # key_version - (required) is a type of string
  key_version = null

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
variable "cluster_id" {
  description = "(required)"
  type        = string
}

variable "key_name" {
  description = "(required)"
  type        = string
}

variable "key_vault_id" {
  description = "(required)"
  type        = string
}

variable "key_version" {
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
resource "azurerm_kusto_cluster_customer_managed_key" "this" {
  cluster_id   = var.cluster_id
  key_name     = var.key_name
  key_vault_id = var.key_vault_id
  key_version  = var.key_version

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
  value       = azurerm_kusto_cluster_customer_managed_key.this.id
}

output "this" {
  value = azurerm_kusto_cluster_customer_managed_key.this
}
```

[top](#index)