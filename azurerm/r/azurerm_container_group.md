# azurerm_container_group

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
module "azurerm_container_group" {
  source = "./modules/azurerm/r/azurerm_container_group"

  # dns_name_label - (optional) is a type of string
  dns_name_label = null
  # ip_address_type - (optional) is a type of string
  ip_address_type = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # network_profile_id - (optional) is a type of string
  network_profile_id = null
  # os_type - (required) is a type of string
  os_type = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # restart_policy - (optional) is a type of string
  restart_policy = null
  # tags - (optional) is a type of map of string
  tags = {}

  container = [{
    commands              = []
    cpu                   = null
    environment_variables = {}
    gpu = [{
      count = null
      sku   = null
    }]
    image = null
    liveness_probe = [{
      exec              = []
      failure_threshold = null
      http_get = [{
        path   = null
        port   = null
        scheme = null
      }]
      initial_delay_seconds = null
      period_seconds        = null
      success_threshold     = null
      timeout_seconds       = null
    }]
    memory = null
    name   = null
    ports = [{
      port     = null
      protocol = null
    }]
    readiness_probe = [{
      exec              = []
      failure_threshold = null
      http_get = [{
        path   = null
        port   = null
        scheme = null
      }]
      initial_delay_seconds = null
      period_seconds        = null
      success_threshold     = null
      timeout_seconds       = null
    }]
    secure_environment_variables = {}
    volume = [{
      empty_dir = null
      git_repo = [{
        directory = null
        revision  = null
        url       = null
      }]
      mount_path           = null
      name                 = null
      read_only            = null
      secret               = {}
      share_name           = null
      storage_account_key  = null
      storage_account_name = null
    }]
  }]

  diagnostics = [{
    log_analytics = [{
      log_type      = null
      metadata      = {}
      workspace_id  = null
      workspace_key = null
    }]
  }]

  dns_config = [{
    nameservers    = []
    options        = []
    search_domains = []
  }]

  identity = [{
    identity_ids = []
    principal_id = null
    type         = null
  }]

  image_registry_credential = [{
    password = null
    server   = null
    username = null
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
variable "dns_name_label" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip_address_type" {
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

variable "network_profile_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "os_type" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "restart_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "container" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      commands              = list(string)
      cpu                   = number
      environment_variables = map(string)
      gpu = list(object(
        {
          count = number
          sku   = string
        }
      ))
      image = string
      liveness_probe = list(object(
        {
          exec              = list(string)
          failure_threshold = number
          http_get = list(object(
            {
              path   = string
              port   = number
              scheme = string
            }
          ))
          initial_delay_seconds = number
          period_seconds        = number
          success_threshold     = number
          timeout_seconds       = number
        }
      ))
      memory = number
      name   = string
      ports = set(object(
        {
          port     = number
          protocol = string
        }
      ))
      readiness_probe = list(object(
        {
          exec              = list(string)
          failure_threshold = number
          http_get = list(object(
            {
              path   = string
              port   = number
              scheme = string
            }
          ))
          initial_delay_seconds = number
          period_seconds        = number
          success_threshold     = number
          timeout_seconds       = number
        }
      ))
      secure_environment_variables = map(string)
      volume = list(object(
        {
          empty_dir = bool
          git_repo = list(object(
            {
              directory = string
              revision  = string
              url       = string
            }
          ))
          mount_path           = string
          name                 = string
          read_only            = bool
          secret               = map(string)
          share_name           = string
          storage_account_key  = string
          storage_account_name = string
        }
      ))
    }
  ))
}

variable "diagnostics" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      log_analytics = list(object(
        {
          log_type      = string
          metadata      = map(string)
          workspace_id  = string
          workspace_key = string
        }
      ))
    }
  ))
  default = []
}

variable "dns_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      nameservers    = list(string)
      options        = set(string)
      search_domains = set(string)
    }
  ))
  default = []
}

variable "identity" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      identity_ids = list(string)
      principal_id = string
      type         = string
    }
  ))
  default = []
}

variable "image_registry_credential" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      password = string
      server   = string
      username = string
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
resource "azurerm_container_group" "this" {
  # dns_name_label - (optional) is a type of string
  dns_name_label = var.dns_name_label
  # ip_address_type - (optional) is a type of string
  ip_address_type = var.ip_address_type
  # location - (required) is a type of string
  location = var.location
  # name - (required) is a type of string
  name = var.name
  # network_profile_id - (optional) is a type of string
  network_profile_id = var.network_profile_id
  # os_type - (required) is a type of string
  os_type = var.os_type
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # restart_policy - (optional) is a type of string
  restart_policy = var.restart_policy
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "container" {
    for_each = var.container
    content {
      # commands - (optional) is a type of list of string
      commands = container.value["commands"]
      # cpu - (required) is a type of number
      cpu = container.value["cpu"]
      # environment_variables - (optional) is a type of map of string
      environment_variables = container.value["environment_variables"]
      # image - (required) is a type of string
      image = container.value["image"]
      # memory - (required) is a type of number
      memory = container.value["memory"]
      # name - (required) is a type of string
      name = container.value["name"]
      # secure_environment_variables - (optional) is a type of map of string
      secure_environment_variables = container.value["secure_environment_variables"]

      dynamic "gpu" {
        for_each = container.value.gpu
        content {
          # count - (optional) is a type of number
          count = gpu.value["count"]
          # sku - (optional) is a type of string
          sku = gpu.value["sku"]
        }
      }

      dynamic "liveness_probe" {
        for_each = container.value.liveness_probe
        content {
          # exec - (optional) is a type of list of string
          exec = liveness_probe.value["exec"]
          # failure_threshold - (optional) is a type of number
          failure_threshold = liveness_probe.value["failure_threshold"]
          # initial_delay_seconds - (optional) is a type of number
          initial_delay_seconds = liveness_probe.value["initial_delay_seconds"]
          # period_seconds - (optional) is a type of number
          period_seconds = liveness_probe.value["period_seconds"]
          # success_threshold - (optional) is a type of number
          success_threshold = liveness_probe.value["success_threshold"]
          # timeout_seconds - (optional) is a type of number
          timeout_seconds = liveness_probe.value["timeout_seconds"]

          dynamic "http_get" {
            for_each = liveness_probe.value.http_get
            content {
              # path - (optional) is a type of string
              path = http_get.value["path"]
              # port - (optional) is a type of number
              port = http_get.value["port"]
              # scheme - (optional) is a type of string
              scheme = http_get.value["scheme"]
            }
          }

        }
      }

      dynamic "ports" {
        for_each = container.value.ports
        content {
          # port - (optional) is a type of number
          port = ports.value["port"]
          # protocol - (optional) is a type of string
          protocol = ports.value["protocol"]
        }
      }

      dynamic "readiness_probe" {
        for_each = container.value.readiness_probe
        content {
          # exec - (optional) is a type of list of string
          exec = readiness_probe.value["exec"]
          # failure_threshold - (optional) is a type of number
          failure_threshold = readiness_probe.value["failure_threshold"]
          # initial_delay_seconds - (optional) is a type of number
          initial_delay_seconds = readiness_probe.value["initial_delay_seconds"]
          # period_seconds - (optional) is a type of number
          period_seconds = readiness_probe.value["period_seconds"]
          # success_threshold - (optional) is a type of number
          success_threshold = readiness_probe.value["success_threshold"]
          # timeout_seconds - (optional) is a type of number
          timeout_seconds = readiness_probe.value["timeout_seconds"]

          dynamic "http_get" {
            for_each = readiness_probe.value.http_get
            content {
              # path - (optional) is a type of string
              path = http_get.value["path"]
              # port - (optional) is a type of number
              port = http_get.value["port"]
              # scheme - (optional) is a type of string
              scheme = http_get.value["scheme"]
            }
          }

        }
      }

      dynamic "volume" {
        for_each = container.value.volume
        content {
          # empty_dir - (optional) is a type of bool
          empty_dir = volume.value["empty_dir"]
          # mount_path - (required) is a type of string
          mount_path = volume.value["mount_path"]
          # name - (required) is a type of string
          name = volume.value["name"]
          # read_only - (optional) is a type of bool
          read_only = volume.value["read_only"]
          # secret - (optional) is a type of map of string
          secret = volume.value["secret"]
          # share_name - (optional) is a type of string
          share_name = volume.value["share_name"]
          # storage_account_key - (optional) is a type of string
          storage_account_key = volume.value["storage_account_key"]
          # storage_account_name - (optional) is a type of string
          storage_account_name = volume.value["storage_account_name"]

          dynamic "git_repo" {
            for_each = volume.value.git_repo
            content {
              # directory - (optional) is a type of string
              directory = git_repo.value["directory"]
              # revision - (optional) is a type of string
              revision = git_repo.value["revision"]
              # url - (required) is a type of string
              url = git_repo.value["url"]
            }
          }

        }
      }

    }
  }

  dynamic "diagnostics" {
    for_each = var.diagnostics
    content {

      dynamic "log_analytics" {
        for_each = diagnostics.value.log_analytics
        content {
          # log_type - (optional) is a type of string
          log_type = log_analytics.value["log_type"]
          # metadata - (optional) is a type of map of string
          metadata = log_analytics.value["metadata"]
          # workspace_id - (required) is a type of string
          workspace_id = log_analytics.value["workspace_id"]
          # workspace_key - (required) is a type of string
          workspace_key = log_analytics.value["workspace_key"]
        }
      }

    }
  }

  dynamic "dns_config" {
    for_each = var.dns_config
    content {
      # nameservers - (required) is a type of list of string
      nameservers = dns_config.value["nameservers"]
      # options - (required) is a type of set of string
      options = dns_config.value["options"]
      # search_domains - (required) is a type of set of string
      search_domains = dns_config.value["search_domains"]
    }
  }

  dynamic "identity" {
    for_each = var.identity
    content {
      # identity_ids - (optional) is a type of list of string
      identity_ids = identity.value["identity_ids"]
      # type - (required) is a type of string
      type = identity.value["type"]
    }
  }

  dynamic "image_registry_credential" {
    for_each = var.image_registry_credential
    content {
      # password - (required) is a type of string
      password = image_registry_credential.value["password"]
      # server - (required) is a type of string
      server = image_registry_credential.value["server"]
      # username - (required) is a type of string
      username = image_registry_credential.value["username"]
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
output "fqdn" {
  description = "returns a string"
  value       = azurerm_container_group.this.fqdn
}

output "id" {
  description = "returns a string"
  value       = azurerm_container_group.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = azurerm_container_group.this.ip_address
}

output "this" {
  value = azurerm_container_group.this
}
```

[top](#index)