# azurerm_frontdoor

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
module "azurerm_frontdoor" {
  source = "./modules/azurerm/r/azurerm_frontdoor"

  # backend_pools_send_receive_timeout_seconds - (optional) is a type of number
  backend_pools_send_receive_timeout_seconds = null
  # enforce_backend_pools_certificate_name_check - (required) is a type of bool
  enforce_backend_pools_certificate_name_check = null
  # friendly_name - (optional) is a type of string
  friendly_name = null
  # load_balancer_enabled - (optional) is a type of bool
  load_balancer_enabled = null
  # location - (optional) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}

  backend_pool = [{
    backend = [{
      address     = null
      enabled     = null
      host_header = null
      http_port   = null
      https_port  = null
      priority    = null
      weight      = null
    }]
    health_probe_name   = null
    id                  = null
    load_balancing_name = null
    name                = null
  }]

  backend_pool_health_probe = [{
    enabled             = null
    id                  = null
    interval_in_seconds = null
    name                = null
    path                = null
    probe_method        = null
    protocol            = null
  }]

  backend_pool_load_balancing = [{
    additional_latency_milliseconds = null
    id                              = null
    name                            = null
    sample_size                     = null
    successful_samples_required     = null
  }]

  frontend_endpoint = [{
    custom_https_configuration = [{
      azure_key_vault_certificate_secret_name    = null
      azure_key_vault_certificate_secret_version = null
      azure_key_vault_certificate_vault_id       = null
      certificate_source                         = null
      minimum_tls_version                        = null
      provisioning_state                         = null
      provisioning_substate                      = null
    }]
    custom_https_provisioning_enabled       = null
    host_name                               = null
    id                                      = null
    name                                    = null
    session_affinity_enabled                = null
    session_affinity_ttl_seconds            = null
    web_application_firewall_policy_link_id = null
  }]

  routing_rule = [{
    accepted_protocols = []
    enabled            = null
    forwarding_configuration = [{
      backend_pool_name                     = null
      cache_enabled                         = null
      cache_query_parameter_strip_directive = null
      cache_use_dynamic_compression         = null
      custom_forwarding_path                = null
      forwarding_protocol                   = null
    }]
    frontend_endpoints = []
    id                 = null
    name               = null
    patterns_to_match  = []
    redirect_configuration = [{
      custom_fragment     = null
      custom_host         = null
      custom_path         = null
      custom_query_string = null
      redirect_protocol   = null
      redirect_type       = null
    }]
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
variable "backend_pools_send_receive_timeout_seconds" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "enforce_backend_pools_certificate_name_check" {
  description = "(required)"
  type        = bool
}

variable "friendly_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "load_balancer_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "location" {
  description = "(optional)"
  type        = string
  default     = null
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

variable "backend_pool" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      backend = list(object(
        {
          address     = string
          enabled     = bool
          host_header = string
          http_port   = number
          https_port  = number
          priority    = number
          weight      = number
        }
      ))
      health_probe_name   = string
      id                  = string
      load_balancing_name = string
      name                = string
    }
  ))
}

variable "backend_pool_health_probe" {
  description = "nested block: NestingList, min items: 1, max items: 5000"
  type = set(object(
    {
      enabled             = bool
      id                  = string
      interval_in_seconds = number
      name                = string
      path                = string
      probe_method        = string
      protocol            = string
    }
  ))
}

variable "backend_pool_load_balancing" {
  description = "nested block: NestingList, min items: 1, max items: 5000"
  type = set(object(
    {
      additional_latency_milliseconds = number
      id                              = string
      name                            = string
      sample_size                     = number
      successful_samples_required     = number
    }
  ))
}

variable "frontend_endpoint" {
  description = "nested block: NestingList, min items: 1, max items: 100"
  type = set(object(
    {
      custom_https_configuration = list(object(
        {
          azure_key_vault_certificate_secret_name    = string
          azure_key_vault_certificate_secret_version = string
          azure_key_vault_certificate_vault_id       = string
          certificate_source                         = string
          minimum_tls_version                        = string
          provisioning_state                         = string
          provisioning_substate                      = string
        }
      ))
      custom_https_provisioning_enabled       = bool
      host_name                               = string
      id                                      = string
      name                                    = string
      session_affinity_enabled                = bool
      session_affinity_ttl_seconds            = number
      web_application_firewall_policy_link_id = string
    }
  ))
}

variable "routing_rule" {
  description = "nested block: NestingList, min items: 1, max items: 100"
  type = set(object(
    {
      accepted_protocols = list(string)
      enabled            = bool
      forwarding_configuration = list(object(
        {
          backend_pool_name                     = string
          cache_enabled                         = bool
          cache_query_parameter_strip_directive = string
          cache_use_dynamic_compression         = bool
          custom_forwarding_path                = string
          forwarding_protocol                   = string
        }
      ))
      frontend_endpoints = list(string)
      id                 = string
      name               = string
      patterns_to_match  = list(string)
      redirect_configuration = list(object(
        {
          custom_fragment     = string
          custom_host         = string
          custom_path         = string
          custom_query_string = string
          redirect_protocol   = string
          redirect_type       = string
        }
      ))
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
resource "azurerm_frontdoor" "this" {
  # backend_pools_send_receive_timeout_seconds - (optional) is a type of number
  backend_pools_send_receive_timeout_seconds = var.backend_pools_send_receive_timeout_seconds
  # enforce_backend_pools_certificate_name_check - (required) is a type of bool
  enforce_backend_pools_certificate_name_check = var.enforce_backend_pools_certificate_name_check
  # friendly_name - (optional) is a type of string
  friendly_name = var.friendly_name
  # load_balancer_enabled - (optional) is a type of bool
  load_balancer_enabled = var.load_balancer_enabled
  # location - (optional) is a type of string
  location = var.location
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "backend_pool" {
    for_each = var.backend_pool
    content {
      # health_probe_name - (required) is a type of string
      health_probe_name = backend_pool.value["health_probe_name"]
      # load_balancing_name - (required) is a type of string
      load_balancing_name = backend_pool.value["load_balancing_name"]
      # name - (required) is a type of string
      name = backend_pool.value["name"]

      dynamic "backend" {
        for_each = backend_pool.value.backend
        content {
          # address - (required) is a type of string
          address = backend.value["address"]
          # enabled - (optional) is a type of bool
          enabled = backend.value["enabled"]
          # host_header - (required) is a type of string
          host_header = backend.value["host_header"]
          # http_port - (required) is a type of number
          http_port = backend.value["http_port"]
          # https_port - (required) is a type of number
          https_port = backend.value["https_port"]
          # priority - (optional) is a type of number
          priority = backend.value["priority"]
          # weight - (optional) is a type of number
          weight = backend.value["weight"]
        }
      }

    }
  }

  dynamic "backend_pool_health_probe" {
    for_each = var.backend_pool_health_probe
    content {
      # enabled - (optional) is a type of bool
      enabled = backend_pool_health_probe.value["enabled"]
      # interval_in_seconds - (optional) is a type of number
      interval_in_seconds = backend_pool_health_probe.value["interval_in_seconds"]
      # name - (required) is a type of string
      name = backend_pool_health_probe.value["name"]
      # path - (optional) is a type of string
      path = backend_pool_health_probe.value["path"]
      # probe_method - (optional) is a type of string
      probe_method = backend_pool_health_probe.value["probe_method"]
      # protocol - (optional) is a type of string
      protocol = backend_pool_health_probe.value["protocol"]
    }
  }

  dynamic "backend_pool_load_balancing" {
    for_each = var.backend_pool_load_balancing
    content {
      # additional_latency_milliseconds - (optional) is a type of number
      additional_latency_milliseconds = backend_pool_load_balancing.value["additional_latency_milliseconds"]
      # name - (required) is a type of string
      name = backend_pool_load_balancing.value["name"]
      # sample_size - (optional) is a type of number
      sample_size = backend_pool_load_balancing.value["sample_size"]
      # successful_samples_required - (optional) is a type of number
      successful_samples_required = backend_pool_load_balancing.value["successful_samples_required"]
    }
  }

  dynamic "frontend_endpoint" {
    for_each = var.frontend_endpoint
    content {
      # custom_https_provisioning_enabled - (optional) is a type of bool
      custom_https_provisioning_enabled = frontend_endpoint.value["custom_https_provisioning_enabled"]
      # host_name - (required) is a type of string
      host_name = frontend_endpoint.value["host_name"]
      # name - (required) is a type of string
      name = frontend_endpoint.value["name"]
      # session_affinity_enabled - (optional) is a type of bool
      session_affinity_enabled = frontend_endpoint.value["session_affinity_enabled"]
      # session_affinity_ttl_seconds - (optional) is a type of number
      session_affinity_ttl_seconds = frontend_endpoint.value["session_affinity_ttl_seconds"]
      # web_application_firewall_policy_link_id - (optional) is a type of string
      web_application_firewall_policy_link_id = frontend_endpoint.value["web_application_firewall_policy_link_id"]

      dynamic "custom_https_configuration" {
        for_each = frontend_endpoint.value.custom_https_configuration
        content {
          # azure_key_vault_certificate_secret_name - (optional) is a type of string
          azure_key_vault_certificate_secret_name = custom_https_configuration.value["azure_key_vault_certificate_secret_name"]
          # azure_key_vault_certificate_secret_version - (optional) is a type of string
          azure_key_vault_certificate_secret_version = custom_https_configuration.value["azure_key_vault_certificate_secret_version"]
          # azure_key_vault_certificate_vault_id - (optional) is a type of string
          azure_key_vault_certificate_vault_id = custom_https_configuration.value["azure_key_vault_certificate_vault_id"]
          # certificate_source - (optional) is a type of string
          certificate_source = custom_https_configuration.value["certificate_source"]
        }
      }

    }
  }

  dynamic "routing_rule" {
    for_each = var.routing_rule
    content {
      # accepted_protocols - (required) is a type of list of string
      accepted_protocols = routing_rule.value["accepted_protocols"]
      # enabled - (optional) is a type of bool
      enabled = routing_rule.value["enabled"]
      # frontend_endpoints - (required) is a type of list of string
      frontend_endpoints = routing_rule.value["frontend_endpoints"]
      # name - (required) is a type of string
      name = routing_rule.value["name"]
      # patterns_to_match - (required) is a type of list of string
      patterns_to_match = routing_rule.value["patterns_to_match"]

      dynamic "forwarding_configuration" {
        for_each = routing_rule.value.forwarding_configuration
        content {
          # backend_pool_name - (required) is a type of string
          backend_pool_name = forwarding_configuration.value["backend_pool_name"]
          # cache_enabled - (optional) is a type of bool
          cache_enabled = forwarding_configuration.value["cache_enabled"]
          # cache_query_parameter_strip_directive - (optional) is a type of string
          cache_query_parameter_strip_directive = forwarding_configuration.value["cache_query_parameter_strip_directive"]
          # cache_use_dynamic_compression - (optional) is a type of bool
          cache_use_dynamic_compression = forwarding_configuration.value["cache_use_dynamic_compression"]
          # custom_forwarding_path - (optional) is a type of string
          custom_forwarding_path = forwarding_configuration.value["custom_forwarding_path"]
          # forwarding_protocol - (optional) is a type of string
          forwarding_protocol = forwarding_configuration.value["forwarding_protocol"]
        }
      }

      dynamic "redirect_configuration" {
        for_each = routing_rule.value.redirect_configuration
        content {
          # custom_fragment - (optional) is a type of string
          custom_fragment = redirect_configuration.value["custom_fragment"]
          # custom_host - (optional) is a type of string
          custom_host = redirect_configuration.value["custom_host"]
          # custom_path - (optional) is a type of string
          custom_path = redirect_configuration.value["custom_path"]
          # custom_query_string - (optional) is a type of string
          custom_query_string = redirect_configuration.value["custom_query_string"]
          # redirect_protocol - (required) is a type of string
          redirect_protocol = redirect_configuration.value["redirect_protocol"]
          # redirect_type - (required) is a type of string
          redirect_type = redirect_configuration.value["redirect_type"]
        }
      }

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
output "backend_pool_health_probes" {
  description = "returns a map of string"
  value       = azurerm_frontdoor.this.backend_pool_health_probes
}

output "backend_pool_load_balancing_settings" {
  description = "returns a map of string"
  value       = azurerm_frontdoor.this.backend_pool_load_balancing_settings
}

output "backend_pools" {
  description = "returns a map of string"
  value       = azurerm_frontdoor.this.backend_pools
}

output "cname" {
  description = "returns a string"
  value       = azurerm_frontdoor.this.cname
}

output "frontend_endpoints" {
  description = "returns a map of string"
  value       = azurerm_frontdoor.this.frontend_endpoints
}

output "header_frontdoor_id" {
  description = "returns a string"
  value       = azurerm_frontdoor.this.header_frontdoor_id
}

output "id" {
  description = "returns a string"
  value       = azurerm_frontdoor.this.id
}

output "location" {
  description = "returns a string"
  value       = azurerm_frontdoor.this.location
}

output "routing_rules" {
  description = "returns a map of string"
  value       = azurerm_frontdoor.this.routing_rules
}

output "this" {
  value = azurerm_frontdoor.this
}
```

[top](#index)