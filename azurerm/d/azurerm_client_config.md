# azurerm_client_config

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
module "azurerm_client_config" {
  source = "./modules/azurerm/d/azurerm_client_config"


  timeouts = [{
    read = null
  }]
}
```

[top](#index)

### Variables

```terraform
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
data "azurerm_client_config" "this" {

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      read = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "client_id" {
  description = "returns a string"
  value       = data.azurerm_client_config.this.client_id
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_client_config.this.id
}

output "object_id" {
  description = "returns a string"
  value       = data.azurerm_client_config.this.object_id
}

output "subscription_id" {
  description = "returns a string"
  value       = data.azurerm_client_config.this.subscription_id
}

output "tenant_id" {
  description = "returns a string"
  value       = data.azurerm_client_config.this.tenant_id
}

output "this" {
  value = azurerm_client_config.this
}
```

[top](#index)