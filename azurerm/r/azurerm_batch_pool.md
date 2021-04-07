# azurerm_batch_pool

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
module "azurerm_batch_pool" {
  source = "./modules/azurerm/r/azurerm_batch_pool"

  # account_name - (required) is a type of string
  account_name = null
  # display_name - (optional) is a type of string
  display_name = null
  # max_tasks_per_node - (optional) is a type of number
  max_tasks_per_node = null
  # metadata - (optional) is a type of map of string
  metadata = {}
  # name - (required) is a type of string
  name = null
  # node_agent_sku_id - (required) is a type of string
  node_agent_sku_id = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # stop_pending_resize_operation - (optional) is a type of bool
  stop_pending_resize_operation = null
  # vm_size - (required) is a type of string
  vm_size = null

  auto_scale = [{
    evaluation_interval = null
    formula             = null
  }]

  certificate = [{
    id             = null
    store_location = null
    store_name     = null
    visibility     = []
  }]

  container_configuration = [{
    container_image_names = []
    container_registries = [{
      password        = null
      registry_server = null
      user_name       = null
    }]
    type = null
  }]

  fixed_scale = [{
    resize_timeout            = null
    target_dedicated_nodes    = null
    target_low_priority_nodes = null
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
    public_address_provisioning_type = null
    public_ips                       = []
    subnet_id                        = null
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

  storage_image_reference = [{
    id        = null
    offer     = null
    publisher = null
    sku       = null
    version   = null
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
variable "account_name" {
  description = "(required)"
  type        = string
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_tasks_per_node" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "metadata" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "node_agent_sku_id" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "stop_pending_resize_operation" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "vm_size" {
  description = "(required)"
  type        = string
}

variable "auto_scale" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      evaluation_interval = string
      formula             = string
    }
  ))
  default = []
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

variable "container_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      container_image_names = set(string)
      container_registries = list(object(
        {
          password        = string
          registry_server = string
          user_name       = string
        }
      ))
      type = string
    }
  ))
  default = []
}

variable "fixed_scale" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      resize_timeout            = string
      target_dedicated_nodes    = number
      target_low_priority_nodes = number
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
      public_address_provisioning_type = string
      public_ips                       = set(string)
      subnet_id                        = string
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

variable "storage_image_reference" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      id        = string
      offer     = string
      publisher = string
      sku       = string
      version   = string
    }
  ))
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
resource "azurerm_batch_pool" "this" {
  # account_name - (required) is a type of string
  account_name = var.account_name
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # max_tasks_per_node - (optional) is a type of number
  max_tasks_per_node = var.max_tasks_per_node
  # metadata - (optional) is a type of map of string
  metadata = var.metadata
  # name - (required) is a type of string
  name = var.name
  # node_agent_sku_id - (required) is a type of string
  node_agent_sku_id = var.node_agent_sku_id
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # stop_pending_resize_operation - (optional) is a type of bool
  stop_pending_resize_operation = var.stop_pending_resize_operation
  # vm_size - (required) is a type of string
  vm_size = var.vm_size

  dynamic "auto_scale" {
    for_each = var.auto_scale
    content {
      # evaluation_interval - (optional) is a type of string
      evaluation_interval = auto_scale.value["evaluation_interval"]
      # formula - (required) is a type of string
      formula = auto_scale.value["formula"]
    }
  }

  dynamic "certificate" {
    for_each = var.certificate
    content {
      # id - (required) is a type of string
      id = certificate.value["id"]
      # store_location - (required) is a type of string
      store_location = certificate.value["store_location"]
      # store_name - (optional) is a type of string
      store_name = certificate.value["store_name"]
      # visibility - (optional) is a type of set of string
      visibility = certificate.value["visibility"]
    }
  }

  dynamic "container_configuration" {
    for_each = var.container_configuration
    content {
      # container_image_names - (optional) is a type of set of string
      container_image_names = container_configuration.value["container_image_names"]
      # container_registries - (optional) is a type of list of object
      container_registries = container_configuration.value["container_registries"]
      # type - (optional) is a type of string
      type = container_configuration.value["type"]
    }
  }

  dynamic "fixed_scale" {
    for_each = var.fixed_scale
    content {
      # resize_timeout - (optional) is a type of string
      resize_timeout = fixed_scale.value["resize_timeout"]
      # target_dedicated_nodes - (optional) is a type of number
      target_dedicated_nodes = fixed_scale.value["target_dedicated_nodes"]
      # target_low_priority_nodes - (optional) is a type of number
      target_low_priority_nodes = fixed_scale.value["target_low_priority_nodes"]
    }
  }

  dynamic "network_configuration" {
    for_each = var.network_configuration
    content {
      # public_address_provisioning_type - (optional) is a type of string
      public_address_provisioning_type = network_configuration.value["public_address_provisioning_type"]
      # public_ips - (optional) is a type of set of string
      public_ips = network_configuration.value["public_ips"]
      # subnet_id - (required) is a type of string
      subnet_id = network_configuration.value["subnet_id"]

      dynamic "endpoint_configuration" {
        for_each = network_configuration.value.endpoint_configuration
        content {
          # backend_port - (required) is a type of number
          backend_port = endpoint_configuration.value["backend_port"]
          # frontend_port_range - (required) is a type of string
          frontend_port_range = endpoint_configuration.value["frontend_port_range"]
          # name - (required) is a type of string
          name = endpoint_configuration.value["name"]
          # protocol - (required) is a type of string
          protocol = endpoint_configuration.value["protocol"]

          dynamic "network_security_group_rules" {
            for_each = endpoint_configuration.value.network_security_group_rules
            content {
              # access - (required) is a type of string
              access = network_security_group_rules.value["access"]
              # priority - (required) is a type of number
              priority = network_security_group_rules.value["priority"]
              # source_address_prefix - (required) is a type of string
              source_address_prefix = network_security_group_rules.value["source_address_prefix"]
            }
          }

        }
      }

    }
  }

  dynamic "start_task" {
    for_each = var.start_task
    content {
      # command_line - (required) is a type of string
      command_line = start_task.value["command_line"]
      # environment - (optional) is a type of map of string
      environment = start_task.value["environment"]
      # max_task_retry_count - (optional) is a type of number
      max_task_retry_count = start_task.value["max_task_retry_count"]
      # wait_for_success - (optional) is a type of bool
      wait_for_success = start_task.value["wait_for_success"]

      dynamic "resource_file" {
        for_each = start_task.value.resource_file
        content {
          # auto_storage_container_name - (optional) is a type of string
          auto_storage_container_name = resource_file.value["auto_storage_container_name"]
          # blob_prefix - (optional) is a type of string
          blob_prefix = resource_file.value["blob_prefix"]
          # file_mode - (optional) is a type of string
          file_mode = resource_file.value["file_mode"]
          # file_path - (optional) is a type of string
          file_path = resource_file.value["file_path"]
          # http_url - (optional) is a type of string
          http_url = resource_file.value["http_url"]
          # storage_container_url - (optional) is a type of string
          storage_container_url = resource_file.value["storage_container_url"]
        }
      }

      dynamic "user_identity" {
        for_each = start_task.value.user_identity
        content {
          # user_name - (optional) is a type of string
          user_name = user_identity.value["user_name"]

          dynamic "auto_user" {
            for_each = user_identity.value.auto_user
            content {
              # elevation_level - (optional) is a type of string
              elevation_level = auto_user.value["elevation_level"]
              # scope - (optional) is a type of string
              scope = auto_user.value["scope"]
            }
          }

        }
      }

    }
  }

  dynamic "storage_image_reference" {
    for_each = var.storage_image_reference
    content {
      # id - (optional) is a type of string
      id = storage_image_reference.value["id"]
      # offer - (optional) is a type of string
      offer = storage_image_reference.value["offer"]
      # publisher - (optional) is a type of string
      publisher = storage_image_reference.value["publisher"]
      # sku - (optional) is a type of string
      sku = storage_image_reference.value["sku"]
      # version - (optional) is a type of string
      version = storage_image_reference.value["version"]
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
  value       = azurerm_batch_pool.this.id
}

output "this" {
  value = azurerm_batch_pool.this
}
```

[top](#index)