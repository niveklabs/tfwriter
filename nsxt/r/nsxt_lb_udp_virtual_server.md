# nsxt_lb_udp_virtual_server

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
module "nsxt_lb_udp_virtual_server" {
  source = "./modules/nsxt/r/nsxt_lb_udp_virtual_server"

  # access_log_enabled - (optional) is a type of bool
  access_log_enabled = null
  # application_profile_id - (required) is a type of string
  application_profile_id = null
  # default_pool_member_ports - (optional) is a type of list of string
  default_pool_member_ports = []
  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # enabled - (optional) is a type of bool
  enabled = null
  # ip_address - (required) is a type of string
  ip_address = null
  # max_concurrent_connections - (optional) is a type of number
  max_concurrent_connections = null
  # max_new_connection_rate - (optional) is a type of number
  max_new_connection_rate = null
  # persistence_profile_id - (optional) is a type of string
  persistence_profile_id = null
  # pool_id - (optional) is a type of string
  pool_id = null
  # ports - (required) is a type of list of string
  ports = []
  # sorry_pool_id - (optional) is a type of string
  sorry_pool_id = null

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
  description = "(optional) - Whether access log is enabled"
  type        = bool
  default     = null
}

variable "application_profile_id" {
  description = "(required) - The tcp application profile defines the application protocol characteristics"
  type        = string
}

variable "default_pool_member_ports" {
  description = "(optional) - Default pool member ports or port range"
  type        = list(string)
  default     = null
}

variable "description" {
  description = "(optional) - Description of this resource"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional) - The display name of this resource. Defaults to ID if not set"
  type        = string
  default     = null
}

variable "enabled" {
  description = "(optional) - whether the virtual server is enabled"
  type        = bool
  default     = null
}

variable "ip_address" {
  description = "(required) - virtual server IP address"
  type        = string
}

variable "max_concurrent_connections" {
  description = "(optional) - If not specified, connections are unlimited"
  type        = number
  default     = null
}

variable "max_new_connection_rate" {
  description = "(optional) - If not specified, connection rate is unlimited"
  type        = number
  default     = null
}

variable "persistence_profile_id" {
  description = "(optional) - Persistence profile is used to allow related client connections to be sent to the same backend server. Source ip persistence is supported."
  type        = string
  default     = null
}

variable "pool_id" {
  description = "(optional) - Server pool for backend connections"
  type        = string
  default     = null
}

variable "ports" {
  description = "(required) - Single port, multiple ports or port ranges"
  type        = list(string)
}

variable "sorry_pool_id" {
  description = "(optional) - When load balancer can not select a backend server to serve the request in default pool, the request would be served by sorry server pool"
  type        = string
  default     = null
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
resource "nsxt_lb_udp_virtual_server" "this" {
  access_log_enabled         = var.access_log_enabled
  application_profile_id     = var.application_profile_id
  default_pool_member_ports  = var.default_pool_member_ports
  description                = var.description
  display_name               = var.display_name
  enabled                    = var.enabled
  ip_address                 = var.ip_address
  max_concurrent_connections = var.max_concurrent_connections
  max_new_connection_rate    = var.max_new_connection_rate
  persistence_profile_id     = var.persistence_profile_id
  pool_id                    = var.pool_id
  ports                      = var.ports
  sorry_pool_id              = var.sorry_pool_id

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
output "display_name" {
  description = "returns a string"
  value       = nsxt_lb_udp_virtual_server.this.display_name
}

output "id" {
  description = "returns a string"
  value       = nsxt_lb_udp_virtual_server.this.id
}

output "revision" {
  description = "returns a number"
  value       = nsxt_lb_udp_virtual_server.this.revision
}

output "this" {
  value = nsxt_lb_udp_virtual_server.this
}
```

[top](#index)