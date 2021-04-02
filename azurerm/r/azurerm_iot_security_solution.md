# azurerm_iot_security_solution

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
module "azurerm_iot_security_solution" {
  source = "./modules/azurerm/r/azurerm_iot_security_solution"

  # display_name - (required) is a type of string
  display_name = null
  # enabled - (optional) is a type of bool
  enabled = null
  # events_to_export - (optional) is a type of set of string
  events_to_export = []
  # iothub_ids - (required) is a type of set of string
  iothub_ids = []
  # location - (required) is a type of string
  location = null
  # log_analytics_workspace_id - (optional) is a type of string
  log_analytics_workspace_id = null
  # log_unmasked_ips_enabled - (optional) is a type of bool
  log_unmasked_ips_enabled = null
  # name - (required) is a type of string
  name = null
  # query_for_resources - (optional) is a type of string
  query_for_resources = null
  # query_subscription_ids - (optional) is a type of set of string
  query_subscription_ids = []
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}

  recommendations_enabled = [{
    acr_authentication               = null
    agent_send_unutilized_msg        = null
    baseline                         = null
    edge_hub_mem_optimize            = null
    edge_logging_option              = null
    inconsistent_module_settings     = null
    install_agent                    = null
    ip_filter_deny_all               = null
    ip_filter_permissive_rule        = null
    open_ports                       = null
    permissive_firewall_policy       = null
    permissive_input_firewall_rules  = null
    permissive_output_firewall_rules = null
    privileged_docker_options        = null
    shared_credentials               = null
    vulnerable_tls_cipher_suite      = null
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
variable "display_name" {
  description = "(required)"
  type        = string
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "events_to_export" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "iothub_ids" {
  description = "(required)"
  type        = set(string)
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "log_analytics_workspace_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "log_unmasked_ips_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "query_for_resources" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "query_subscription_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
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

variable "recommendations_enabled" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      acr_authentication               = bool
      agent_send_unutilized_msg        = bool
      baseline                         = bool
      edge_hub_mem_optimize            = bool
      edge_logging_option              = bool
      inconsistent_module_settings     = bool
      install_agent                    = bool
      ip_filter_deny_all               = bool
      ip_filter_permissive_rule        = bool
      open_ports                       = bool
      permissive_firewall_policy       = bool
      permissive_input_firewall_rules  = bool
      permissive_output_firewall_rules = bool
      privileged_docker_options        = bool
      shared_credentials               = bool
      vulnerable_tls_cipher_suite      = bool
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
resource "azurerm_iot_security_solution" "this" {
  display_name               = var.display_name
  enabled                    = var.enabled
  events_to_export           = var.events_to_export
  iothub_ids                 = var.iothub_ids
  location                   = var.location
  log_analytics_workspace_id = var.log_analytics_workspace_id
  log_unmasked_ips_enabled   = var.log_unmasked_ips_enabled
  name                       = var.name
  query_for_resources        = var.query_for_resources
  query_subscription_ids     = var.query_subscription_ids
  resource_group_name        = var.resource_group_name
  tags                       = var.tags

  dynamic "recommendations_enabled" {
    for_each = var.recommendations_enabled
    content {
      acr_authentication               = recommendations_enabled.value["acr_authentication"]
      agent_send_unutilized_msg        = recommendations_enabled.value["agent_send_unutilized_msg"]
      baseline                         = recommendations_enabled.value["baseline"]
      edge_hub_mem_optimize            = recommendations_enabled.value["edge_hub_mem_optimize"]
      edge_logging_option              = recommendations_enabled.value["edge_logging_option"]
      inconsistent_module_settings     = recommendations_enabled.value["inconsistent_module_settings"]
      install_agent                    = recommendations_enabled.value["install_agent"]
      ip_filter_deny_all               = recommendations_enabled.value["ip_filter_deny_all"]
      ip_filter_permissive_rule        = recommendations_enabled.value["ip_filter_permissive_rule"]
      open_ports                       = recommendations_enabled.value["open_ports"]
      permissive_firewall_policy       = recommendations_enabled.value["permissive_firewall_policy"]
      permissive_input_firewall_rules  = recommendations_enabled.value["permissive_input_firewall_rules"]
      permissive_output_firewall_rules = recommendations_enabled.value["permissive_output_firewall_rules"]
      privileged_docker_options        = recommendations_enabled.value["privileged_docker_options"]
      shared_credentials               = recommendations_enabled.value["shared_credentials"]
      vulnerable_tls_cipher_suite      = recommendations_enabled.value["vulnerable_tls_cipher_suite"]
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
output "id" {
  description = "returns a string"
  value       = azurerm_iot_security_solution.this.id
}

output "query_for_resources" {
  description = "returns a string"
  value       = azurerm_iot_security_solution.this.query_for_resources
}

output "query_subscription_ids" {
  description = "returns a set of string"
  value       = azurerm_iot_security_solution.this.query_subscription_ids
}

output "this" {
  value = azurerm_iot_security_solution.this
}
```

[top](#index)