# nsxt_policy_lb_virtual_server

[back](../nsxt.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nsxt = ">= 3.1.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nsxt_policy_lb_virtual_server" {
  source = "./modules/nsxt/r/nsxt_policy_lb_virtual_server"

  # access_log_enabled - (optional) is a type of bool
  access_log_enabled = null
  # application_profile_path - (required) is a type of string
  application_profile_path = null
  # default_pool_member_ports - (optional) is a type of list of string
  default_pool_member_ports = []
  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # enabled - (optional) is a type of bool
  enabled = null
  # ip_address - (required) is a type of string
  ip_address = null
  # log_significant_event_only - (optional) is a type of bool
  log_significant_event_only = null
  # max_concurrent_connections - (optional) is a type of number
  max_concurrent_connections = null
  # max_new_connection_rate - (optional) is a type of number
  max_new_connection_rate = null
  # nsx_id - (optional) is a type of string
  nsx_id = null
  # persistence_profile_path - (optional) is a type of string
  persistence_profile_path = null
  # pool_path - (optional) is a type of string
  pool_path = null
  # ports - (required) is a type of list of string
  ports = []
  # service_path - (optional) is a type of string
  service_path = null
  # sorry_pool_path - (optional) is a type of string
  sorry_pool_path = null

  access_list_control = [{
    action     = null
    enabled    = null
    group_path = null
  }]

  client_ssl = [{
    ca_paths                 = []
    certificate_chain_depth  = null
    client_auth              = null
    crl_paths                = []
    default_certificate_path = null
    sni_paths                = []
    ssl_profile_path         = null
  }]

  server_ssl = [{
    ca_paths                = []
    certificate_chain_depth = null
    client_certificate_path = null
    crl_paths               = []
    server_auth             = null
    ssl_profile_path        = null
  }]

  tag = [{
    scope = null
    tag   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "access_log_enabled" {
  description = "(optional) - If enabled, all connections/requests sent to virtual server are logged to the access log file"
  type        = bool
  default     = null
}

variable "application_profile_path" {
  description = "(required) - Application profile for this virtual server"
  type        = string
}

variable "default_pool_member_ports" {
  description = "(optional) - Default pool member ports when member port is not defined"
  type        = list(string)
  default     = null
}

variable "description" {
  description = "(optional) - Description for this resource"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(required) - Display name for this resource"
  type        = string
}

variable "enabled" {
  description = "(optional) - Flag to enable Virtual Server"
  type        = bool
  default     = null
}

variable "ip_address" {
  description = "(required) - Virtual Server IP address"
  type        = string
}

variable "log_significant_event_only" {
  description = "(optional) - Flag to log significant events in access log, if access log is enabed"
  type        = bool
  default     = null
}

variable "max_concurrent_connections" {
  description = "(optional) - To ensure one virtual server does not over consume resources, connections to a virtual server can be capped."
  type        = number
  default     = null
}

variable "max_new_connection_rate" {
  description = "(optional) - To ensure one virtual server does not over consume resources, connections to a member can be rate limited."
  type        = number
  default     = null
}

variable "nsx_id" {
  description = "(optional) - NSX ID for this resource"
  type        = string
  default     = null
}

variable "persistence_profile_path" {
  description = "(optional) - Path to persistence profile allowing related client connections to be sent to the same backend server."
  type        = string
  default     = null
}

variable "pool_path" {
  description = "(optional) - Path for Load Balancer Pool"
  type        = string
  default     = null
}

variable "ports" {
  description = "(required) - Virtual Server ports"
  type        = list(string)
}

variable "service_path" {
  description = "(optional) - Virtual Server can be associated with Load Balancer Service"
  type        = string
  default     = null
}

variable "sorry_pool_path" {
  description = "(optional) - When load balancer can not select server in default pool or pool in rules, the request would be served by sorry pool"
  type        = string
  default     = null
}

variable "access_list_control" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      action     = string
      enabled    = bool
      group_path = string
    }
  ))
  default = []
}

variable "client_ssl" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      ca_paths                 = list(string)
      certificate_chain_depth  = number
      client_auth              = string
      crl_paths                = list(string)
      default_certificate_path = string
      sni_paths                = list(string)
      ssl_profile_path         = string
    }
  ))
  default = []
}

variable "server_ssl" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      ca_paths                = list(string)
      certificate_chain_depth = number
      client_certificate_path = string
      crl_paths               = list(string)
      server_auth             = string
      ssl_profile_path        = string
    }
  ))
  default = []
}

variable "tag" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      scope = string
      tag   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "nsxt_policy_lb_virtual_server" "this" {
  access_log_enabled         = var.access_log_enabled
  application_profile_path   = var.application_profile_path
  default_pool_member_ports  = var.default_pool_member_ports
  description                = var.description
  display_name               = var.display_name
  enabled                    = var.enabled
  ip_address                 = var.ip_address
  log_significant_event_only = var.log_significant_event_only
  max_concurrent_connections = var.max_concurrent_connections
  max_new_connection_rate    = var.max_new_connection_rate
  nsx_id                     = var.nsx_id
  persistence_profile_path   = var.persistence_profile_path
  pool_path                  = var.pool_path
  ports                      = var.ports
  service_path               = var.service_path
  sorry_pool_path            = var.sorry_pool_path

  dynamic "access_list_control" {
    for_each = var.access_list_control
    content {
      action     = access_list_control.value["action"]
      enabled    = access_list_control.value["enabled"]
      group_path = access_list_control.value["group_path"]
    }
  }

  dynamic "client_ssl" {
    for_each = var.client_ssl
    content {
      ca_paths                 = client_ssl.value["ca_paths"]
      certificate_chain_depth  = client_ssl.value["certificate_chain_depth"]
      client_auth              = client_ssl.value["client_auth"]
      crl_paths                = client_ssl.value["crl_paths"]
      default_certificate_path = client_ssl.value["default_certificate_path"]
      sni_paths                = client_ssl.value["sni_paths"]
      ssl_profile_path         = client_ssl.value["ssl_profile_path"]
    }
  }

  dynamic "server_ssl" {
    for_each = var.server_ssl
    content {
      ca_paths                = server_ssl.value["ca_paths"]
      certificate_chain_depth = server_ssl.value["certificate_chain_depth"]
      client_certificate_path = server_ssl.value["client_certificate_path"]
      crl_paths               = server_ssl.value["crl_paths"]
      server_auth             = server_ssl.value["server_auth"]
      ssl_profile_path        = server_ssl.value["ssl_profile_path"]
    }
  }

  dynamic "tag" {
    for_each = var.tag
    content {
      scope = tag.value["scope"]
      tag   = tag.value["tag"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = nsxt_policy_lb_virtual_server.this.id
}

output "nsx_id" {
  description = "returns a string"
  value       = nsxt_policy_lb_virtual_server.this.nsx_id
}

output "path" {
  description = "returns a string"
  value       = nsxt_policy_lb_virtual_server.this.path
}

output "revision" {
  description = "returns a number"
  value       = nsxt_policy_lb_virtual_server.this.revision
}

output "this" {
  value = nsxt_policy_lb_virtual_server.this
}
```

[top](#index)