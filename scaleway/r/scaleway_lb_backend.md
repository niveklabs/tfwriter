# scaleway_lb_backend

[back](../scaleway.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    scaleway = ">= 2.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "scaleway_lb_backend" {
  source = "./modules/scaleway/r/scaleway_lb_backend"

  # forward_port - (required) is a type of number
  forward_port = null
  # forward_port_algorithm - (optional) is a type of string
  forward_port_algorithm = null
  # forward_protocol - (required) is a type of string
  forward_protocol = null
  # health_check_delay - (optional) is a type of string
  health_check_delay = null
  # health_check_max_retries - (optional) is a type of number
  health_check_max_retries = null
  # health_check_port - (optional) is a type of number
  health_check_port = null
  # health_check_timeout - (optional) is a type of string
  health_check_timeout = null
  # lb_id - (required) is a type of string
  lb_id = null
  # name - (optional) is a type of string
  name = null
  # on_marked_down_action - (optional) is a type of string
  on_marked_down_action = null
  # proxy_protocol - (optional) is a type of string
  proxy_protocol = null
  # send_proxy_v2 - (optional) is a type of bool
  send_proxy_v2 = null
  # server_ips - (optional) is a type of list of string
  server_ips = []
  # sticky_sessions - (optional) is a type of string
  sticky_sessions = null
  # sticky_sessions_cookie_name - (optional) is a type of string
  sticky_sessions_cookie_name = null
  # timeout_connect - (optional) is a type of string
  timeout_connect = null
  # timeout_server - (optional) is a type of string
  timeout_server = null
  # timeout_tunnel - (optional) is a type of string
  timeout_tunnel = null

  health_check_http = [{
    code   = null
    method = null
    uri    = null
  }]

  health_check_https = [{
    code   = null
    method = null
    uri    = null
  }]

  health_check_tcp = [{

  }]

  timeouts = [{
    default = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "forward_port" {
  description = "(required) - User sessions will be forwarded to this port of backend servers"
  type        = number
}

variable "forward_port_algorithm" {
  description = "(optional) - Load balancing algorithm"
  type        = string
  default     = null
}

variable "forward_protocol" {
  description = "(required) - Backend protocol"
  type        = string
}

variable "health_check_delay" {
  description = "(optional) - Interval between two HC requests"
  type        = string
  default     = null
}

variable "health_check_max_retries" {
  description = "(optional) - Number of allowed failed HC requests before the backend server is marked down"
  type        = number
  default     = null
}

variable "health_check_port" {
  description = "(optional) - Port the HC requests will be send to. Default to `forward_port`"
  type        = number
  default     = null
}

variable "health_check_timeout" {
  description = "(optional) - Timeout before we consider a HC request failed"
  type        = string
  default     = null
}

variable "lb_id" {
  description = "(required) - The load-balancer ID"
  type        = string
}

variable "name" {
  description = "(optional) - The name of the backend"
  type        = string
  default     = null
}

variable "on_marked_down_action" {
  description = "(optional) - Modify what occurs when a backend server is marked down"
  type        = string
  default     = null
}

variable "proxy_protocol" {
  description = "(optional) - Type of PROXY protocol to enable"
  type        = string
  default     = null
}

variable "send_proxy_v2" {
  description = "(optional) - Enables PROXY protocol version 2"
  type        = bool
  default     = null
}

variable "server_ips" {
  description = "(optional) - Backend server IP addresses list (IPv4 or IPv6)"
  type        = list(string)
  default     = null
}

variable "sticky_sessions" {
  description = "(optional) - Load balancing algorithm"
  type        = string
  default     = null
}

variable "sticky_sessions_cookie_name" {
  description = "(optional) - Cookie name for for sticky sessions"
  type        = string
  default     = null
}

variable "timeout_connect" {
  description = "(optional) - Maximum initial server connection establishment time"
  type        = string
  default     = null
}

variable "timeout_server" {
  description = "(optional) - Maximum server connection inactivity time"
  type        = string
  default     = null
}

variable "timeout_tunnel" {
  description = "(optional) - Maximum tunnel inactivity time"
  type        = string
  default     = null
}

variable "health_check_http" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      code   = number
      method = string
      uri    = string
    }
  ))
  default = []
}

variable "health_check_https" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      code   = number
      method = string
      uri    = string
    }
  ))
  default = []
}

variable "health_check_tcp" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {

    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      default = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "scaleway_lb_backend" "this" {
  forward_port                = var.forward_port
  forward_port_algorithm      = var.forward_port_algorithm
  forward_protocol            = var.forward_protocol
  health_check_delay          = var.health_check_delay
  health_check_max_retries    = var.health_check_max_retries
  health_check_port           = var.health_check_port
  health_check_timeout        = var.health_check_timeout
  lb_id                       = var.lb_id
  name                        = var.name
  on_marked_down_action       = var.on_marked_down_action
  proxy_protocol              = var.proxy_protocol
  send_proxy_v2               = var.send_proxy_v2
  server_ips                  = var.server_ips
  sticky_sessions             = var.sticky_sessions
  sticky_sessions_cookie_name = var.sticky_sessions_cookie_name
  timeout_connect             = var.timeout_connect
  timeout_server              = var.timeout_server
  timeout_tunnel              = var.timeout_tunnel

  dynamic "health_check_http" {
    for_each = var.health_check_http
    content {
      code   = health_check_http.value["code"]
      method = health_check_http.value["method"]
      uri    = health_check_http.value["uri"]
    }
  }

  dynamic "health_check_https" {
    for_each = var.health_check_https
    content {
      code   = health_check_https.value["code"]
      method = health_check_https.value["method"]
      uri    = health_check_https.value["uri"]
    }
  }

  dynamic "health_check_tcp" {
    for_each = var.health_check_tcp
    content {
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      default = timeouts.value["default"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "health_check_port" {
  description = "returns a number"
  value       = scaleway_lb_backend.this.health_check_port
}

output "id" {
  description = "returns a string"
  value       = scaleway_lb_backend.this.id
}

output "name" {
  description = "returns a string"
  value       = scaleway_lb_backend.this.name
}

output "this" {
  value = scaleway_lb_backend.this
}
```

[top](#index)