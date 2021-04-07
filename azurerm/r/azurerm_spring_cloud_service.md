# azurerm_spring_cloud_service

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
module "azurerm_spring_cloud_service" {
  source = "./modules/azurerm/r/azurerm_spring_cloud_service"

  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # sku_name - (optional) is a type of string
  sku_name = null
  # tags - (optional) is a type of map of string
  tags = {}

  config_server_git_setting = [{
    http_basic_auth = [{
      password = null
      username = null
    }]
    label = null
    repository = [{
      http_basic_auth = [{
        password = null
        username = null
      }]
      label        = null
      name         = null
      pattern      = []
      search_paths = []
      ssh_auth = [{
        host_key                         = null
        host_key_algorithm               = null
        private_key                      = null
        strict_host_key_checking_enabled = null
      }]
      uri = null
    }]
    search_paths = []
    ssh_auth = [{
      host_key                         = null
      host_key_algorithm               = null
      private_key                      = null
      strict_host_key_checking_enabled = null
    }]
    uri = null
  }]

  network = [{
    app_network_resource_group             = null
    app_subnet_id                          = null
    cidr_ranges                            = []
    service_runtime_network_resource_group = null
    service_runtime_subnet_id              = null
  }]

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]

  trace = [{
    instrumentation_key = null
    sample_rate         = null
  }]
}
```

[top](#index)

### Variables

```terraform
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

variable "sku_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "config_server_git_setting" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      http_basic_auth = list(object(
        {
          password = string
          username = string
        }
      ))
      label = string
      repository = list(object(
        {
          http_basic_auth = list(object(
            {
              password = string
              username = string
            }
          ))
          label        = string
          name         = string
          pattern      = list(string)
          search_paths = list(string)
          ssh_auth = list(object(
            {
              host_key                         = string
              host_key_algorithm               = string
              private_key                      = string
              strict_host_key_checking_enabled = bool
            }
          ))
          uri = string
        }
      ))
      search_paths = list(string)
      ssh_auth = list(object(
        {
          host_key                         = string
          host_key_algorithm               = string
          private_key                      = string
          strict_host_key_checking_enabled = bool
        }
      ))
      uri = string
    }
  ))
  default = []
}

variable "network" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      app_network_resource_group             = string
      app_subnet_id                          = string
      cidr_ranges                            = list(string)
      service_runtime_network_resource_group = string
      service_runtime_subnet_id              = string
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

variable "trace" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      instrumentation_key = string
      sample_rate         = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_spring_cloud_service" "this" {
  # location - (required) is a type of string
  location = var.location
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # sku_name - (optional) is a type of string
  sku_name = var.sku_name
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "config_server_git_setting" {
    for_each = var.config_server_git_setting
    content {
      # label - (optional) is a type of string
      label = config_server_git_setting.value["label"]
      # search_paths - (optional) is a type of list of string
      search_paths = config_server_git_setting.value["search_paths"]
      # uri - (required) is a type of string
      uri = config_server_git_setting.value["uri"]

      dynamic "http_basic_auth" {
        for_each = config_server_git_setting.value.http_basic_auth
        content {
          # password - (required) is a type of string
          password = http_basic_auth.value["password"]
          # username - (required) is a type of string
          username = http_basic_auth.value["username"]
        }
      }

      dynamic "repository" {
        for_each = config_server_git_setting.value.repository
        content {
          # label - (optional) is a type of string
          label = repository.value["label"]
          # name - (required) is a type of string
          name = repository.value["name"]
          # pattern - (optional) is a type of list of string
          pattern = repository.value["pattern"]
          # search_paths - (optional) is a type of list of string
          search_paths = repository.value["search_paths"]
          # uri - (required) is a type of string
          uri = repository.value["uri"]

          dynamic "http_basic_auth" {
            for_each = repository.value.http_basic_auth
            content {
              # password - (required) is a type of string
              password = http_basic_auth.value["password"]
              # username - (required) is a type of string
              username = http_basic_auth.value["username"]
            }
          }

          dynamic "ssh_auth" {
            for_each = repository.value.ssh_auth
            content {
              # host_key - (optional) is a type of string
              host_key = ssh_auth.value["host_key"]
              # host_key_algorithm - (optional) is a type of string
              host_key_algorithm = ssh_auth.value["host_key_algorithm"]
              # private_key - (required) is a type of string
              private_key = ssh_auth.value["private_key"]
              # strict_host_key_checking_enabled - (optional) is a type of bool
              strict_host_key_checking_enabled = ssh_auth.value["strict_host_key_checking_enabled"]
            }
          }

        }
      }

      dynamic "ssh_auth" {
        for_each = config_server_git_setting.value.ssh_auth
        content {
          # host_key - (optional) is a type of string
          host_key = ssh_auth.value["host_key"]
          # host_key_algorithm - (optional) is a type of string
          host_key_algorithm = ssh_auth.value["host_key_algorithm"]
          # private_key - (required) is a type of string
          private_key = ssh_auth.value["private_key"]
          # strict_host_key_checking_enabled - (optional) is a type of bool
          strict_host_key_checking_enabled = ssh_auth.value["strict_host_key_checking_enabled"]
        }
      }

    }
  }

  dynamic "network" {
    for_each = var.network
    content {
      # app_network_resource_group - (optional) is a type of string
      app_network_resource_group = network.value["app_network_resource_group"]
      # app_subnet_id - (required) is a type of string
      app_subnet_id = network.value["app_subnet_id"]
      # cidr_ranges - (required) is a type of list of string
      cidr_ranges = network.value["cidr_ranges"]
      # service_runtime_network_resource_group - (optional) is a type of string
      service_runtime_network_resource_group = network.value["service_runtime_network_resource_group"]
      # service_runtime_subnet_id - (required) is a type of string
      service_runtime_subnet_id = network.value["service_runtime_subnet_id"]
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

  dynamic "trace" {
    for_each = var.trace
    content {
      # instrumentation_key - (required) is a type of string
      instrumentation_key = trace.value["instrumentation_key"]
      # sample_rate - (optional) is a type of number
      sample_rate = trace.value["sample_rate"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurerm_spring_cloud_service.this.id
}

output "outbound_public_ip_addresses" {
  description = "returns a list of string"
  value       = azurerm_spring_cloud_service.this.outbound_public_ip_addresses
}

output "this" {
  value = azurerm_spring_cloud_service.this
}
```

[top](#index)