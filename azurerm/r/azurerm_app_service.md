# azurerm_app_service

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
module "azurerm_app_service" {
  source = "./modules/azurerm/r/azurerm_app_service"

  # app_service_plan_id - (required) is a type of string
  app_service_plan_id = null
  # app_settings - (optional) is a type of map of string
  app_settings = {}
  # client_affinity_enabled - (optional) is a type of bool
  client_affinity_enabled = null
  # client_cert_enabled - (optional) is a type of bool
  client_cert_enabled = null
  # enabled - (optional) is a type of bool
  enabled = null
  # https_only - (optional) is a type of bool
  https_only = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}

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

  backup = [{
    enabled = null
    name    = null
    schedule = [{
      frequency_interval       = null
      frequency_unit           = null
      keep_at_least_one_backup = null
      retention_period_in_days = null
      start_time               = null
    }]
    storage_account_url = null
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

  logs = [{
    application_logs = [{
      azure_blob_storage = [{
        level             = null
        retention_in_days = null
        sas_url           = null
      }]
      file_system_level = null
    }]
    http_logs = [{
      azure_blob_storage = [{
        retention_in_days = null
        sas_url           = null
      }]
      file_system = [{
        retention_in_days = null
        retention_in_mb   = null
      }]
    }]
  }]

  site_config = [{
    always_on           = null
    app_command_line    = null
    auto_swap_slot_name = null
    cors = [{
      allowed_origins     = []
      support_credentials = null
    }]
    default_documents        = []
    dotnet_framework_version = null
    ftps_state               = null
    health_check_path        = null
    http2_enabled            = null
    ip_restriction = [{
      action                    = null
      ip_address                = null
      name                      = null
      priority                  = null
      subnet_id                 = null
      virtual_network_subnet_id = null
    }]
    java_container           = null
    java_container_version   = null
    java_version             = null
    linux_fx_version         = null
    local_mysql_enabled      = null
    managed_pipeline_mode    = null
    min_tls_version          = null
    php_version              = null
    python_version           = null
    remote_debugging_enabled = null
    remote_debugging_version = null
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
    windows_fx_version          = null
  }]

  source_control = [{
    branch             = null
    manual_integration = null
    repo_url           = null
    rollback_enabled   = null
    use_mercurial      = null
  }]

  storage_account = [{
    access_key   = null
    account_name = null
    mount_path   = null
    name         = null
    share_name   = null
    type         = null
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

variable "client_cert_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
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

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
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

variable "backup" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enabled = bool
      name    = string
      schedule = list(object(
        {
          frequency_interval       = number
          frequency_unit           = string
          keep_at_least_one_backup = bool
          retention_period_in_days = number
          start_time               = string
        }
      ))
      storage_account_url = string
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

variable "logs" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      application_logs = list(object(
        {
          azure_blob_storage = list(object(
            {
              level             = string
              retention_in_days = number
              sas_url           = string
            }
          ))
          file_system_level = string
        }
      ))
      http_logs = list(object(
        {
          azure_blob_storage = list(object(
            {
              retention_in_days = number
              sas_url           = string
            }
          ))
          file_system = list(object(
            {
              retention_in_days = number
              retention_in_mb   = number
            }
          ))
        }
      ))
    }
  ))
  default = []
}

variable "site_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      always_on           = bool
      app_command_line    = string
      auto_swap_slot_name = string
      cors = list(object(
        {
          allowed_origins     = set(string)
          support_credentials = bool
        }
      ))
      default_documents        = list(string)
      dotnet_framework_version = string
      ftps_state               = string
      health_check_path        = string
      http2_enabled            = bool
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
      java_container           = string
      java_container_version   = string
      java_version             = string
      linux_fx_version         = string
      local_mysql_enabled      = bool
      managed_pipeline_mode    = string
      min_tls_version          = string
      php_version              = string
      python_version           = string
      remote_debugging_enabled = bool
      remote_debugging_version = string
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
      windows_fx_version          = string
    }
  ))
  default = []
}

variable "source_control" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      branch             = string
      manual_integration = bool
      repo_url           = string
      rollback_enabled   = bool
      use_mercurial      = bool
    }
  ))
  default = []
}

variable "storage_account" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      access_key   = string
      account_name = string
      mount_path   = string
      name         = string
      share_name   = string
      type         = string
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
resource "azurerm_app_service" "this" {
  app_service_plan_id     = var.app_service_plan_id
  app_settings            = var.app_settings
  client_affinity_enabled = var.client_affinity_enabled
  client_cert_enabled     = var.client_cert_enabled
  enabled                 = var.enabled
  https_only              = var.https_only
  location                = var.location
  name                    = var.name
  resource_group_name     = var.resource_group_name
  tags                    = var.tags

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

  dynamic "backup" {
    for_each = var.backup
    content {
      enabled             = backup.value["enabled"]
      name                = backup.value["name"]
      storage_account_url = backup.value["storage_account_url"]

      dynamic "schedule" {
        for_each = backup.value.schedule
        content {
          frequency_interval       = schedule.value["frequency_interval"]
          frequency_unit           = schedule.value["frequency_unit"]
          keep_at_least_one_backup = schedule.value["keep_at_least_one_backup"]
          retention_period_in_days = schedule.value["retention_period_in_days"]
          start_time               = schedule.value["start_time"]
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

  dynamic "logs" {
    for_each = var.logs
    content {

      dynamic "application_logs" {
        for_each = logs.value.application_logs
        content {
          file_system_level = application_logs.value["file_system_level"]

          dynamic "azure_blob_storage" {
            for_each = application_logs.value.azure_blob_storage
            content {
              level             = azure_blob_storage.value["level"]
              retention_in_days = azure_blob_storage.value["retention_in_days"]
              sas_url           = azure_blob_storage.value["sas_url"]
            }
          }

        }
      }

      dynamic "http_logs" {
        for_each = logs.value.http_logs
        content {

          dynamic "azure_blob_storage" {
            for_each = http_logs.value.azure_blob_storage
            content {
              retention_in_days = azure_blob_storage.value["retention_in_days"]
              sas_url           = azure_blob_storage.value["sas_url"]
            }
          }

          dynamic "file_system" {
            for_each = http_logs.value.file_system
            content {
              retention_in_days = file_system.value["retention_in_days"]
              retention_in_mb   = file_system.value["retention_in_mb"]
            }
          }

        }
      }

    }
  }

  dynamic "site_config" {
    for_each = var.site_config
    content {
      always_on                   = site_config.value["always_on"]
      app_command_line            = site_config.value["app_command_line"]
      auto_swap_slot_name         = site_config.value["auto_swap_slot_name"]
      default_documents           = site_config.value["default_documents"]
      dotnet_framework_version    = site_config.value["dotnet_framework_version"]
      ftps_state                  = site_config.value["ftps_state"]
      health_check_path           = site_config.value["health_check_path"]
      http2_enabled               = site_config.value["http2_enabled"]
      ip_restriction              = site_config.value["ip_restriction"]
      java_container              = site_config.value["java_container"]
      java_container_version      = site_config.value["java_container_version"]
      java_version                = site_config.value["java_version"]
      linux_fx_version            = site_config.value["linux_fx_version"]
      local_mysql_enabled         = site_config.value["local_mysql_enabled"]
      managed_pipeline_mode       = site_config.value["managed_pipeline_mode"]
      min_tls_version             = site_config.value["min_tls_version"]
      php_version                 = site_config.value["php_version"]
      python_version              = site_config.value["python_version"]
      remote_debugging_enabled    = site_config.value["remote_debugging_enabled"]
      remote_debugging_version    = site_config.value["remote_debugging_version"]
      scm_ip_restriction          = site_config.value["scm_ip_restriction"]
      scm_type                    = site_config.value["scm_type"]
      scm_use_main_ip_restriction = site_config.value["scm_use_main_ip_restriction"]
      use_32_bit_worker_process   = site_config.value["use_32_bit_worker_process"]
      websockets_enabled          = site_config.value["websockets_enabled"]
      windows_fx_version          = site_config.value["windows_fx_version"]

      dynamic "cors" {
        for_each = site_config.value.cors
        content {
          allowed_origins     = cors.value["allowed_origins"]
          support_credentials = cors.value["support_credentials"]
        }
      }

    }
  }

  dynamic "source_control" {
    for_each = var.source_control
    content {
      branch             = source_control.value["branch"]
      manual_integration = source_control.value["manual_integration"]
      repo_url           = source_control.value["repo_url"]
      rollback_enabled   = source_control.value["rollback_enabled"]
      use_mercurial      = source_control.value["use_mercurial"]
    }
  }

  dynamic "storage_account" {
    for_each = var.storage_account
    content {
      access_key   = storage_account.value["access_key"]
      account_name = storage_account.value["account_name"]
      mount_path   = storage_account.value["mount_path"]
      name         = storage_account.value["name"]
      share_name   = storage_account.value["share_name"]
      type         = storage_account.value["type"]
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
  value       = azurerm_app_service.this.app_settings
}

output "custom_domain_verification_id" {
  description = "returns a string"
  value       = azurerm_app_service.this.custom_domain_verification_id
}

output "default_site_hostname" {
  description = "returns a string"
  value       = azurerm_app_service.this.default_site_hostname
}

output "id" {
  description = "returns a string"
  value       = azurerm_app_service.this.id
}

output "outbound_ip_address_list" {
  description = "returns a list of string"
  value       = azurerm_app_service.this.outbound_ip_address_list
}

output "outbound_ip_addresses" {
  description = "returns a string"
  value       = azurerm_app_service.this.outbound_ip_addresses
}

output "possible_outbound_ip_address_list" {
  description = "returns a list of string"
  value       = azurerm_app_service.this.possible_outbound_ip_address_list
}

output "possible_outbound_ip_addresses" {
  description = "returns a string"
  value       = azurerm_app_service.this.possible_outbound_ip_addresses
}

output "site_credential" {
  description = "returns a list of object"
  value       = azurerm_app_service.this.site_credential
}

output "this" {
  value = azurerm_app_service.this
}
```

[top](#index)