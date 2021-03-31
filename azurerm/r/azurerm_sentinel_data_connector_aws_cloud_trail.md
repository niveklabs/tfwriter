# azurerm_sentinel_data_connector_aws_cloud_trail

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
module "azurerm_sentinel_data_connector_aws_cloud_trail" {
  source = "./modules/azurerm/r/azurerm_sentinel_data_connector_aws_cloud_trail"

  # aws_role_arn - (required) is a type of string
  aws_role_arn = null
  # log_analytics_workspace_id - (required) is a type of string
  log_analytics_workspace_id = null
  # name - (required) is a type of string
  name = null

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
variable "aws_role_arn" {
  description = "(required)"
  type        = string
}

variable "log_analytics_workspace_id" {
  description = "(required)"
  type        = string
}

variable "name" {
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
resource "azurerm_sentinel_data_connector_aws_cloud_trail" "this" {
  aws_role_arn               = var.aws_role_arn
  log_analytics_workspace_id = var.log_analytics_workspace_id
  name                       = var.name

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
  value       = azurerm_sentinel_data_connector_aws_cloud_trail.this.id
}

output "this" {
  value = azurerm_sentinel_data_connector_aws_cloud_trail.this
}
```

[top](#index)