# azurerm_batch_pool

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
    azurerm = ">= 2.41.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_batch_pool" {
  source = "./modules/azurerm/d/azurerm_batch_pool"

  # account_name - (required) is a type of string
  account_name = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null

  certificate = [{
    id             = null
    store_location = null
    store_name     = null
    visibility     = []
  }]

  network_configuration = [{
    endpoint_configuration = [{
      backend_port        = null
      frontend_port_range = null
      name                = null
      network_security_group_rules = [{
        access                = null
        priority              = null
        source_address_prefix = null
      }]
      protocol = null
    }]
    subnet_id = null
  }]

  start_task = [{
    command_line         = null
    environment          = {}
    max_task_retry_count = null
    resource_file = [{
      auto_storage_container_name = null
      blob_prefix                 = null
      file_mode                   = null
      file_path                   = null
      http_url                    = null
      storage_container_url       = null
    }]
    user_identity = [{
      auto_user = [{
        elevation_level = null
        scope           = null
      }]
      user_name = null
    }]
    wait_for_success = null
  }]

  timeouts = [{
    read = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "account_name" {
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

variable "certificate" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id             = string
      store_location = string
      store_name     = string
      visibility     = set(string)
    }
  ))
  default = []
}

variable "network_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      endpoint_configuration = list(object(
        {
          backend_port        = number
          frontend_port_range = string
          name                = string
          network_security_group_rules = list(object(
            {
              access                = string
              priority              = number
              source_address_prefix = string
            }
          ))
          protocol = string
        }
      ))
      subnet_id = string
    }
  ))
  default = []
}

variable "start_task" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      command_line         = string
      environment          = map(string)
      max_task_retry_count = number
      resource_file = list(object(
        {
          auto_storage_container_name = string
          blob_prefix                 = string
          file_mode                   = string
          file_path                   = string
          http_url                    = string
          storage_container_url       = string
        }
      ))
      user_identity = list(object(
        {
          auto_user = list(object(
            {
              elevation_level = string
              scope           = string
            }
          ))
          user_name = string
        }
      ))
      wait_for_success = bool
    }
  ))
  default = []
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
data "azurerm_batch_pool" "this" {
  account_name        = var.account_name
  name                = var.name
  resource_group_name = var.resource_group_name

  dynamic "certificate" {
    for_each = var.certificate
    content {
      id             = certificate.value["id"]
      store_location = certificate.value["store_location"]
      store_name     = certificate.value["store_name"]
      visibility     = certificate.value["visibility"]
    }
  }

  dynamic "network_configuration" {
    for_each = var.network_configuration
    content {
      subnet_id = network_configuration.value["subnet_id"]

      dynamic "endpoint_configuration" {
        for_each = network_configuration.value.endpoint_configuration
        content {

          dynamic "network_security_group_rules" {
            for_each = endpoint_configuration.value.network_security_group_rules
            content {
            }
          }

        }
      }

    }
  }

  dynamic "start_task" {
    for_each = var.start_task
    content {
      command_line         = start_task.value["command_line"]
      environment          = start_task.value["environment"]
      max_task_retry_count = start_task.value["max_task_retry_count"]
      wait_for_success     = start_task.value["wait_for_success"]
    }
  }

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
output "auto_scale" {
  description = "returns a list of object"
  value       = data.azurerm_batch_pool.this.auto_scale
}

output "container_configuration" {
  description = "returns a list of object"
  value       = data.azurerm_batch_pool.this.container_configuration
}

output "display_name" {
  description = "returns a string"
  value       = data.azurerm_batch_pool.this.display_name
}

output "fixed_scale" {
  description = "returns a list of object"
  value       = data.azurerm_batch_pool.this.fixed_scale
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_batch_pool.this.id
}

output "max_tasks_per_node" {
  description = "returns a number"
  value       = data.azurerm_batch_pool.this.max_tasks_per_node
}

output "metadata" {
  description = "returns a map of string"
  value       = data.azurerm_batch_pool.this.metadata
}

output "node_agent_sku_id" {
  description = "returns a string"
  value       = data.azurerm_batch_pool.this.node_agent_sku_id
}

output "storage_image_reference" {
  description = "returns a list of object"
  value       = data.azurerm_batch_pool.this.storage_image_reference
}

output "vm_size" {
  description = "returns a string"
  value       = data.azurerm_batch_pool.this.vm_size
}

output "this" {
  value = azurerm_batch_pool.this
}
```

[top](#index)