# azurerm_function_app_slot

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
module "azurerm_function_app_slot" {
  source = "./modules/azurerm/r/azurerm_function_app_slot"

  # app_service_plan_id - (required) is a type of string
  app_service_plan_id = null
  # app_settings - (optional) is a type of map of string
  app_settings = {}
  # client_affinity_enabled - (optional) is a type of bool
  client_affinity_enabled = null
  # daily_memory_time_quota - (optional) is a type of number
  daily_memory_time_quota = null
  # enable_builtin_logging - (optional) is a type of bool
  enable_builtin_logging = null
  # enabled - (optional) is a type of bool
  enabled = null
  # function_app_name - (required) is a type of string
  function_app_name = null
  # https_only - (optional) is a type of bool
  https_only = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # os_type - (optional) is a type of string
  os_type = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # storage_account_access_key - (required) is a type of string
  storage_account_access_key = null
  # storage_account_name - (required) is a type of string
  storage_account_name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # version - (optional) is a type of string
  version = null

  auth_settings = [{
    active_directory = [{
      allowed_audiences = []
      client_id         = null
      client_secret     = null
    }]
    additional_login_params        = {}
    allowed_external_redirect_urls = []
    default_provider               = null
    enabled                        = null
    facebook = [{
      app_id       = null
      app_secret   = null
      oauth_scopes = []
    }]
    google = [{
      client_id     = null
      client_secret = null
      oauth_scopes  = []
    }]
    issuer = null
    microsoft = [{
      client_id     = null
      client_secret = null
      oauth_scopes  = []
    }]
    runtime_version               = null
    token_refresh_extension_hours = null
    token_store_enabled           = null
    twitter = [{
      consumer_key    = null
      consumer_secret = null
    }]
    unauthenticated_client_action = null
  }]

  connection_string = [{
    name  = null
    type  = null
    value = null
  }]

  identity = [{
    identity_ids = []
    principal_id = null
    tenant_id    = null
    type         = null
  }]

  site_config = [{
    always_on           = null
    auto_swap_slot_name = null
    cors = [{
      allowed_origins     = []
      support_credentials = null
    }]
    ftps_state        = null
    health_check_path = null
    http2_enabled     = null
    ip_restriction = [{
      action                    = null
      ip_address                = null
      name                      = null
      priority                  = null
      subnet_id                 = null
      virtual_network_subnet_id = null
    }]
    linux_fx_version          = null
    min_tls_version           = null
    pre_warmed_instance_count = null
    scm_ip_restriction = [{
      action                    = null
      ip_address                = null
      name                      = null
      priority                  = null
      subnet_id                 = null
      virtual_network_subnet_id = null
    }]
    scm_type                    = null
    scm_use_main_ip_restriction = null
    use_32_bit_worker_process   = null
    websockets_enabled          = null
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
variable "app_service_plan_id" {
  description = "(required)"
  type        = string
}

variable "app_settings" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "client_affinity_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "daily_memory_time_quota" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "enable_builtin_logging" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "function_app_name" {
  description = "(required)"
  type        = string
}

variable "https_only" {
  description = "(optional)"
  type        = bool
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

variable "os_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "storage_account_access_key" {
  description = "(required)"
  type        = string
}

variable "storage_account_name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_settings" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      active_directory = list(object(
        {
          allowed_audiences = list(string)
          client_id         = string
          client_secret     = string
        }
      ))
      additional_login_params        = map(string)
      allowed_external_redirect_urls = list(string)
      default_provider               = string
      enabled                        = bool
      facebook = list(object(
        {
          app_id       = string
          app_secret   = string
          oauth_scopes = list(string)
        }
      ))
      google = list(object(
        {
          client_id     = string
          client_secret = string
          oauth_scopes  = list(string)
        }
      ))
      issuer = string
      microsoft = list(object(
        {
          client_id     = string
          client_secret = string
          oauth_scopes  = list(string)
        }
      ))
      runtime_version               = string
      token_refresh_extension_hours = number
      token_store_enabled           = bool
      twitter = list(object(
        {
          consumer_key    = string
          consumer_secret = string
        }
      ))
      unauthenticated_client_action = string
    }
  ))
  default = []
}

variable "connection_string" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name  = string
      type  = string
      value = string
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
      tenant_id    = string
      type         = string
    }
  ))
  default = []
}

variable "site_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      always_on           = bool
      auto_swap_slot_name = string
      cors = list(object(
        {
          allowed_origins     = set(string)
          support_credentials = bool
        }
      ))
      ftps_state        = string
      health_check_path = string
      http2_enabled     = bool
      ip_restriction = list(object(
        {
          action                    = string
          ip_address                = string
          name                      = string
          priority                  = number
          subnet_id                 = string
          virtual_network_subnet_id = string
        }
      ))
      linux_fx_version          = string
      min_tls_version           = string
      pre_warmed_instance_count = number
      scm_ip_restriction = list(object(
        {
          action                    = string
          ip_address                = string
          name                      = string
          priority                  = number
          subnet_id                 = string
          virtual_network_subnet_id = string
        }
      ))
      scm_type                    = string
      scm_use_main_ip_restriction = bool
      use_32_bit_worker_process   = bool
      websockets_enabled          = bool
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
resource "azurerm_function_app_slot" "this" {
  app_service_plan_id        = var.app_service_plan_id
  app_settings               = var.app_settings
  client_affinity_enabled    = var.client_affinity_enabled
  daily_memory_time_quota    = var.daily_memory_time_quota
  enable_builtin_logging     = var.enable_builtin_logging
  enabled                    = var.enabled
  function_app_name          = var.function_app_name
  https_only                 = var.https_only
  location                   = var.location
  name                       = var.name
  os_type                    = var.os_type
  resource_group_name        = var.resource_group_name
  storage_account_access_key = var.storage_account_access_key
  storage_account_name       = var.storage_account_name
  tags                       = var.tags
  version                    = var.version

  dynamic "auth_settings" {
    for_each = var.auth_settings
    content {
      additional_login_params        = auth_settings.value["additional_login_params"]
      allowed_external_redirect_urls = auth_settings.value["allowed_external_redirect_urls"]
      default_provider               = auth_settings.value["default_provider"]
      enabled                        = auth_settings.value["enabled"]
      issuer                         = auth_settings.value["issuer"]
      runtime_version                = auth_settings.value["runtime_version"]
      token_refresh_extension_hours  = auth_settings.value["token_refresh_extension_hours"]
      token_store_enabled            = auth_settings.value["token_store_enabled"]
      unauthenticated_client_action  = auth_settings.value["unauthenticated_client_action"]

      dynamic "active_directory" {
        for_each = auth_settings.value.active_directory
        content {
          allowed_audiences = active_directory.value["allowed_audiences"]
          client_id         = active_directory.value["client_id"]
          client_secret     = active_directory.value["client_secret"]
        }
      }

      dynamic "facebook" {
        for_each = auth_settings.value.facebook
        content {
          app_id       = facebook.value["app_id"]
          app_secret   = facebook.value["app_secret"]
          oauth_scopes = facebook.value["oauth_scopes"]
        }
      }

      dynamic "google" {
        for_each = auth_settings.value.google
        content {
          client_id     = google.value["client_id"]
          client_secret = google.value["client_secret"]
          oauth_scopes  = google.value["oauth_scopes"]
        }
      }

      dynamic "microsoft" {
        for_each = auth_settings.value.microsoft
        content {
          client_id     = microsoft.value["client_id"]
          client_secret = microsoft.value["client_secret"]
          oauth_scopes  = microsoft.value["oauth_scopes"]
        }
      }

      dynamic "twitter" {
        for_each = auth_settings.value.twitter
        content {
          consumer_key    = twitter.value["consumer_key"]
          consumer_secret = twitter.value["consumer_secret"]
        }
      }

    }
  }

  dynamic "connection_string" {
    for_each = var.connection_string
    content {
      name  = connection_string.value["name"]
      type  = connection_string.value["type"]
      value = connection_string.value["value"]
    }
  }

  dynamic "identity" {
    for_each = var.identity
    content {
      identity_ids = identity.value["identity_ids"]
      type         = identity.value["type"]
    }
  }

  dynamic "site_config" {
    for_each = var.site_config
    content {
      always_on                   = site_config.value["always_on"]
      auto_swap_slot_name         = site_config.value["auto_swap_slot_name"]
      ftps_state                  = site_config.value["ftps_state"]
      health_check_path           = site_config.value["health_check_path"]
      http2_enabled               = site_config.value["http2_enabled"]
      ip_restriction              = site_config.value["ip_restriction"]
      linux_fx_version            = site_config.value["linux_fx_version"]
      min_tls_version             = site_config.value["min_tls_version"]
      pre_warmed_instance_count   = site_config.value["pre_warmed_instance_count"]
      scm_ip_restriction          = site_config.value["scm_ip_restriction"]
      scm_type                    = site_config.value["scm_type"]
      scm_use_main_ip_restriction = site_config.value["scm_use_main_ip_restriction"]
      use_32_bit_worker_process   = site_config.value["use_32_bit_worker_process"]
      websockets_enabled          = site_config.value["websockets_enabled"]

      dynamic "cors" {
        for_each = site_config.value.cors
        content {
          allowed_origins     = cors.value["allowed_origins"]
          support_credentials = cors.value["support_credentials"]
        }
      }

    }
  }

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
output "app_settings" {
  description = "returns a map of string"
  value       = azurerm_function_app_slot.this.app_settings
}

output "client_affinity_enabled" {
  description = "returns a bool"
  value       = azurerm_function_app_slot.this.client_affinity_enabled
}

output "default_hostname" {
  description = "returns a string"
  value       = azurerm_function_app_slot.this.default_hostname
}

output "id" {
  description = "returns a string"
  value       = azurerm_function_app_slot.this.id
}

output "kind" {
  description = "returns a string"
  value       = azurerm_function_app_slot.this.kind
}

output "outbound_ip_addresses" {
  description = "returns a string"
  value       = azurerm_function_app_slot.this.outbound_ip_addresses
}

output "possible_outbound_ip_addresses" {
  description = "returns a string"
  value       = azurerm_function_app_slot.this.possible_outbound_ip_addresses
}

output "site_credential" {
  description = "returns a list of object"
  value       = azurerm_function_app_slot.this.site_credential
}

output "this" {
  value = azurerm_function_app_slot.this
}
```

[top](#index)