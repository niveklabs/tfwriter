# fortios_user_radius

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_user_radius" {
  source = "./modules/fortios/r/fortios_user_radius"

  # acct_all_servers - (optional) is a type of string
  acct_all_servers = null
  # acct_interim_interval - (optional) is a type of number
  acct_interim_interval = null
  # all_usergroup - (optional) is a type of string
  all_usergroup = null
  # auth_type - (optional) is a type of string
  auth_type = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # group_override_attr_type - (optional) is a type of string
  group_override_attr_type = null
  # h3c_compatibility - (optional) is a type of string
  h3c_compatibility = null
  # interface - (optional) is a type of string
  interface = null
  # interface_select_method - (optional) is a type of string
  interface_select_method = null
  # name - (optional) is a type of string
  name = null
  # nas_ip - (optional) is a type of string
  nas_ip = null
  # password_encoding - (optional) is a type of string
  password_encoding = null
  # password_renewal - (optional) is a type of string
  password_renewal = null
  # radius_coa - (optional) is a type of string
  radius_coa = null
  # radius_port - (optional) is a type of number
  radius_port = null
  # rsso - (optional) is a type of string
  rsso = null
  # rsso_context_timeout - (optional) is a type of number
  rsso_context_timeout = null
  # rsso_endpoint_attribute - (optional) is a type of string
  rsso_endpoint_attribute = null
  # rsso_endpoint_block_attribute - (optional) is a type of string
  rsso_endpoint_block_attribute = null
  # rsso_ep_one_ip_only - (optional) is a type of string
  rsso_ep_one_ip_only = null
  # rsso_flush_ip_session - (optional) is a type of string
  rsso_flush_ip_session = null
  # rsso_log_flags - (optional) is a type of string
  rsso_log_flags = null
  # rsso_log_period - (optional) is a type of number
  rsso_log_period = null
  # rsso_radius_response - (optional) is a type of string
  rsso_radius_response = null
  # rsso_radius_server_port - (optional) is a type of number
  rsso_radius_server_port = null
  # rsso_secret - (optional) is a type of string
  rsso_secret = null
  # rsso_validate_request_secret - (optional) is a type of string
  rsso_validate_request_secret = null
  # secondary_secret - (optional) is a type of string
  secondary_secret = null
  # secondary_server - (optional) is a type of string
  secondary_server = null
  # secret - (optional) is a type of string
  secret = null
  # server - (optional) is a type of string
  server = null
  # source_ip - (optional) is a type of string
  source_ip = null
  # sso_attribute - (optional) is a type of string
  sso_attribute = null
  # sso_attribute_key - (optional) is a type of string
  sso_attribute_key = null
  # sso_attribute_value_override - (optional) is a type of string
  sso_attribute_value_override = null
  # switch_controller_acct_fast_framedip_detect - (optional) is a type of number
  switch_controller_acct_fast_framedip_detect = null
  # switch_controller_service_type - (optional) is a type of string
  switch_controller_service_type = null
  # tertiary_secret - (optional) is a type of string
  tertiary_secret = null
  # tertiary_server - (optional) is a type of string
  tertiary_server = null
  # timeout - (optional) is a type of number
  timeout = null
  # use_management_vdom - (optional) is a type of string
  use_management_vdom = null
  # username_case_sensitive - (optional) is a type of string
  username_case_sensitive = null

  accounting_server = [{
    id                      = null
    interface               = null
    interface_select_method = null
    port                    = null
    secret                  = null
    server                  = null
    source_ip               = null
    status                  = null
  }]

  class = [{
    name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "acct_all_servers" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "acct_interim_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "all_usergroup" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group_override_attr_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "h3c_compatibility" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "interface" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "interface_select_method" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "nas_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "password_encoding" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "password_renewal" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "radius_coa" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "radius_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "rsso" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rsso_context_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "rsso_endpoint_attribute" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rsso_endpoint_block_attribute" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rsso_ep_one_ip_only" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rsso_flush_ip_session" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rsso_log_flags" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rsso_log_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "rsso_radius_response" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rsso_radius_server_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "rsso_secret" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rsso_validate_request_secret" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "secondary_secret" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "secondary_server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "secret" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sso_attribute" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sso_attribute_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sso_attribute_value_override" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "switch_controller_acct_fast_framedip_detect" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "switch_controller_service_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tertiary_secret" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tertiary_server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "use_management_vdom" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "username_case_sensitive" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "accounting_server" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id                      = number
      interface               = string
      interface_select_method = string
      port                    = number
      secret                  = string
      server                  = string
      source_ip               = string
      status                  = string
    }
  ))
  default = []
}

variable "class" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_user_radius" "this" {
  # acct_all_servers - (optional) is a type of string
  acct_all_servers = var.acct_all_servers
  # acct_interim_interval - (optional) is a type of number
  acct_interim_interval = var.acct_interim_interval
  # all_usergroup - (optional) is a type of string
  all_usergroup = var.all_usergroup
  # auth_type - (optional) is a type of string
  auth_type = var.auth_type
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # group_override_attr_type - (optional) is a type of string
  group_override_attr_type = var.group_override_attr_type
  # h3c_compatibility - (optional) is a type of string
  h3c_compatibility = var.h3c_compatibility
  # interface - (optional) is a type of string
  interface = var.interface
  # interface_select_method - (optional) is a type of string
  interface_select_method = var.interface_select_method
  # name - (optional) is a type of string
  name = var.name
  # nas_ip - (optional) is a type of string
  nas_ip = var.nas_ip
  # password_encoding - (optional) is a type of string
  password_encoding = var.password_encoding
  # password_renewal - (optional) is a type of string
  password_renewal = var.password_renewal
  # radius_coa - (optional) is a type of string
  radius_coa = var.radius_coa
  # radius_port - (optional) is a type of number
  radius_port = var.radius_port
  # rsso - (optional) is a type of string
  rsso = var.rsso
  # rsso_context_timeout - (optional) is a type of number
  rsso_context_timeout = var.rsso_context_timeout
  # rsso_endpoint_attribute - (optional) is a type of string
  rsso_endpoint_attribute = var.rsso_endpoint_attribute
  # rsso_endpoint_block_attribute - (optional) is a type of string
  rsso_endpoint_block_attribute = var.rsso_endpoint_block_attribute
  # rsso_ep_one_ip_only - (optional) is a type of string
  rsso_ep_one_ip_only = var.rsso_ep_one_ip_only
  # rsso_flush_ip_session - (optional) is a type of string
  rsso_flush_ip_session = var.rsso_flush_ip_session
  # rsso_log_flags - (optional) is a type of string
  rsso_log_flags = var.rsso_log_flags
  # rsso_log_period - (optional) is a type of number
  rsso_log_period = var.rsso_log_period
  # rsso_radius_response - (optional) is a type of string
  rsso_radius_response = var.rsso_radius_response
  # rsso_radius_server_port - (optional) is a type of number
  rsso_radius_server_port = var.rsso_radius_server_port
  # rsso_secret - (optional) is a type of string
  rsso_secret = var.rsso_secret
  # rsso_validate_request_secret - (optional) is a type of string
  rsso_validate_request_secret = var.rsso_validate_request_secret
  # secondary_secret - (optional) is a type of string
  secondary_secret = var.secondary_secret
  # secondary_server - (optional) is a type of string
  secondary_server = var.secondary_server
  # secret - (optional) is a type of string
  secret = var.secret
  # server - (optional) is a type of string
  server = var.server
  # source_ip - (optional) is a type of string
  source_ip = var.source_ip
  # sso_attribute - (optional) is a type of string
  sso_attribute = var.sso_attribute
  # sso_attribute_key - (optional) is a type of string
  sso_attribute_key = var.sso_attribute_key
  # sso_attribute_value_override - (optional) is a type of string
  sso_attribute_value_override = var.sso_attribute_value_override
  # switch_controller_acct_fast_framedip_detect - (optional) is a type of number
  switch_controller_acct_fast_framedip_detect = var.switch_controller_acct_fast_framedip_detect
  # switch_controller_service_type - (optional) is a type of string
  switch_controller_service_type = var.switch_controller_service_type
  # tertiary_secret - (optional) is a type of string
  tertiary_secret = var.tertiary_secret
  # tertiary_server - (optional) is a type of string
  tertiary_server = var.tertiary_server
  # timeout - (optional) is a type of number
  timeout = var.timeout
  # use_management_vdom - (optional) is a type of string
  use_management_vdom = var.use_management_vdom
  # username_case_sensitive - (optional) is a type of string
  username_case_sensitive = var.username_case_sensitive

  dynamic "accounting_server" {
    for_each = var.accounting_server
    content {
      # id - (optional) is a type of number
      id = accounting_server.value["id"]
      # interface - (optional) is a type of string
      interface = accounting_server.value["interface"]
      # interface_select_method - (optional) is a type of string
      interface_select_method = accounting_server.value["interface_select_method"]
      # port - (optional) is a type of number
      port = accounting_server.value["port"]
      # secret - (optional) is a type of string
      secret = accounting_server.value["secret"]
      # server - (optional) is a type of string
      server = accounting_server.value["server"]
      # source_ip - (optional) is a type of string
      source_ip = accounting_server.value["source_ip"]
      # status - (optional) is a type of string
      status = accounting_server.value["status"]
    }
  }

  dynamic "class" {
    for_each = var.class
    content {
      # name - (optional) is a type of string
      name = class.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "acct_all_servers" {
  description = "returns a string"
  value       = fortios_user_radius.this.acct_all_servers
}

output "acct_interim_interval" {
  description = "returns a number"
  value       = fortios_user_radius.this.acct_interim_interval
}

output "all_usergroup" {
  description = "returns a string"
  value       = fortios_user_radius.this.all_usergroup
}

output "auth_type" {
  description = "returns a string"
  value       = fortios_user_radius.this.auth_type
}

output "group_override_attr_type" {
  description = "returns a string"
  value       = fortios_user_radius.this.group_override_attr_type
}

output "h3c_compatibility" {
  description = "returns a string"
  value       = fortios_user_radius.this.h3c_compatibility
}

output "id" {
  description = "returns a string"
  value       = fortios_user_radius.this.id
}

output "interface" {
  description = "returns a string"
  value       = fortios_user_radius.this.interface
}

output "interface_select_method" {
  description = "returns a string"
  value       = fortios_user_radius.this.interface_select_method
}

output "name" {
  description = "returns a string"
  value       = fortios_user_radius.this.name
}

output "nas_ip" {
  description = "returns a string"
  value       = fortios_user_radius.this.nas_ip
}

output "password_encoding" {
  description = "returns a string"
  value       = fortios_user_radius.this.password_encoding
}

output "password_renewal" {
  description = "returns a string"
  value       = fortios_user_radius.this.password_renewal
}

output "radius_coa" {
  description = "returns a string"
  value       = fortios_user_radius.this.radius_coa
}

output "radius_port" {
  description = "returns a number"
  value       = fortios_user_radius.this.radius_port
}

output "rsso" {
  description = "returns a string"
  value       = fortios_user_radius.this.rsso
}

output "rsso_context_timeout" {
  description = "returns a number"
  value       = fortios_user_radius.this.rsso_context_timeout
}

output "rsso_endpoint_attribute" {
  description = "returns a string"
  value       = fortios_user_radius.this.rsso_endpoint_attribute
}

output "rsso_endpoint_block_attribute" {
  description = "returns a string"
  value       = fortios_user_radius.this.rsso_endpoint_block_attribute
}

output "rsso_ep_one_ip_only" {
  description = "returns a string"
  value       = fortios_user_radius.this.rsso_ep_one_ip_only
}

output "rsso_flush_ip_session" {
  description = "returns a string"
  value       = fortios_user_radius.this.rsso_flush_ip_session
}

output "rsso_log_flags" {
  description = "returns a string"
  value       = fortios_user_radius.this.rsso_log_flags
}

output "rsso_log_period" {
  description = "returns a number"
  value       = fortios_user_radius.this.rsso_log_period
}

output "rsso_radius_response" {
  description = "returns a string"
  value       = fortios_user_radius.this.rsso_radius_response
}

output "rsso_radius_server_port" {
  description = "returns a number"
  value       = fortios_user_radius.this.rsso_radius_server_port
}

output "rsso_validate_request_secret" {
  description = "returns a string"
  value       = fortios_user_radius.this.rsso_validate_request_secret
}

output "secondary_server" {
  description = "returns a string"
  value       = fortios_user_radius.this.secondary_server
}

output "server" {
  description = "returns a string"
  value       = fortios_user_radius.this.server
}

output "source_ip" {
  description = "returns a string"
  value       = fortios_user_radius.this.source_ip
}

output "sso_attribute" {
  description = "returns a string"
  value       = fortios_user_radius.this.sso_attribute
}

output "sso_attribute_key" {
  description = "returns a string"
  value       = fortios_user_radius.this.sso_attribute_key
  sensitive   = true
}

output "sso_attribute_value_override" {
  description = "returns a string"
  value       = fortios_user_radius.this.sso_attribute_value_override
}

output "switch_controller_acct_fast_framedip_detect" {
  description = "returns a number"
  value       = fortios_user_radius.this.switch_controller_acct_fast_framedip_detect
}

output "switch_controller_service_type" {
  description = "returns a string"
  value       = fortios_user_radius.this.switch_controller_service_type
}

output "tertiary_server" {
  description = "returns a string"
  value       = fortios_user_radius.this.tertiary_server
}

output "timeout" {
  description = "returns a number"
  value       = fortios_user_radius.this.timeout
}

output "use_management_vdom" {
  description = "returns a string"
  value       = fortios_user_radius.this.use_management_vdom
}

output "username_case_sensitive" {
  description = "returns a string"
  value       = fortios_user_radius.this.username_case_sensitive
}

output "this" {
  value = fortios_user_radius.this
}
```

[top](#index)