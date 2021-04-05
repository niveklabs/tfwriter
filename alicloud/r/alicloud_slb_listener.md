# alicloud_slb_listener

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_slb_listener" {
  source = "./modules/alicloud/r/alicloud_slb_listener"

  # acl_id - (optional) is a type of string
  acl_id = null
  # acl_status - (optional) is a type of string
  acl_status = null
  # acl_type - (optional) is a type of string
  acl_type = null
  # backend_port - (optional) is a type of number
  backend_port = null
  # bandwidth - (optional) is a type of number
  bandwidth = null
  # ca_certificate_id - (optional) is a type of string
  ca_certificate_id = null
  # cookie - (optional) is a type of string
  cookie = null
  # cookie_timeout - (optional) is a type of number
  cookie_timeout = null
  # delete_protection_validation - (optional) is a type of bool
  delete_protection_validation = null
  # description - (optional) is a type of string
  description = null
  # enable_http2 - (optional) is a type of string
  enable_http2 = null
  # established_timeout - (optional) is a type of number
  established_timeout = null
  # forward_port - (optional) is a type of number
  forward_port = null
  # frontend_port - (required) is a type of number
  frontend_port = null
  # gzip - (optional) is a type of bool
  gzip = null
  # health_check - (optional) is a type of string
  health_check = null
  # health_check_connect_port - (optional) is a type of number
  health_check_connect_port = null
  # health_check_domain - (optional) is a type of string
  health_check_domain = null
  # health_check_http_code - (optional) is a type of string
  health_check_http_code = null
  # health_check_interval - (optional) is a type of number
  health_check_interval = null
  # health_check_method - (optional) is a type of string
  health_check_method = null
  # health_check_timeout - (optional) is a type of number
  health_check_timeout = null
  # health_check_type - (optional) is a type of string
  health_check_type = null
  # health_check_uri - (optional) is a type of string
  health_check_uri = null
  # healthy_threshold - (optional) is a type of number
  healthy_threshold = null
  # idle_timeout - (optional) is a type of number
  idle_timeout = null
  # instance_port - (optional) is a type of number
  instance_port = null
  # lb_port - (optional) is a type of number
  lb_port = null
  # lb_protocol - (optional) is a type of string
  lb_protocol = null
  # listener_forward - (optional) is a type of string
  listener_forward = null
  # load_balancer_id - (required) is a type of string
  load_balancer_id = null
  # master_slave_server_group_id - (optional) is a type of string
  master_slave_server_group_id = null
  # persistence_timeout - (optional) is a type of number
  persistence_timeout = null
  # protocol - (required) is a type of string
  protocol = null
  # request_timeout - (optional) is a type of number
  request_timeout = null
  # scheduler - (optional) is a type of string
  scheduler = null
  # server_certificate_id - (optional) is a type of string
  server_certificate_id = null
  # server_group_id - (optional) is a type of string
  server_group_id = null
  # ssl_certificate_id - (optional) is a type of string
  ssl_certificate_id = null
  # sticky_session - (optional) is a type of string
  sticky_session = null
  # sticky_session_type - (optional) is a type of string
  sticky_session_type = null
  # tls_cipher_policy - (optional) is a type of string
  tls_cipher_policy = null
  # unhealthy_threshold - (optional) is a type of number
  unhealthy_threshold = null

  x_forwarded_for = [{
    retrive_client_ip = null
    retrive_slb_id    = null
    retrive_slb_ip    = null
    retrive_slb_proto = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "acl_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "acl_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "acl_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "backend_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "bandwidth" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ca_certificate_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cookie" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cookie_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "delete_protection_validation" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable_http2" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "established_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "forward_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "frontend_port" {
  description = "(required)"
  type        = number
}

variable "gzip" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "health_check" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "health_check_connect_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "health_check_domain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "health_check_http_code" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "health_check_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "health_check_method" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "health_check_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "health_check_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "health_check_uri" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "healthy_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "idle_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "instance_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "lb_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "lb_protocol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "listener_forward" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "load_balancer_id" {
  description = "(required)"
  type        = string
}

variable "master_slave_server_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "persistence_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "protocol" {
  description = "(required)"
  type        = string
}

variable "request_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "scheduler" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server_certificate_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_certificate_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sticky_session" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sticky_session_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tls_cipher_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "unhealthy_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "x_forwarded_for" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      retrive_client_ip = bool
      retrive_slb_id    = bool
      retrive_slb_ip    = bool
      retrive_slb_proto = bool
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_slb_listener" "this" {
  acl_id                       = var.acl_id
  acl_status                   = var.acl_status
  acl_type                     = var.acl_type
  backend_port                 = var.backend_port
  bandwidth                    = var.bandwidth
  ca_certificate_id            = var.ca_certificate_id
  cookie                       = var.cookie
  cookie_timeout               = var.cookie_timeout
  delete_protection_validation = var.delete_protection_validation
  description                  = var.description
  enable_http2                 = var.enable_http2
  established_timeout          = var.established_timeout
  forward_port                 = var.forward_port
  frontend_port                = var.frontend_port
  gzip                         = var.gzip
  health_check                 = var.health_check
  health_check_connect_port    = var.health_check_connect_port
  health_check_domain          = var.health_check_domain
  health_check_http_code       = var.health_check_http_code
  health_check_interval        = var.health_check_interval
  health_check_method          = var.health_check_method
  health_check_timeout         = var.health_check_timeout
  health_check_type            = var.health_check_type
  health_check_uri             = var.health_check_uri
  healthy_threshold            = var.healthy_threshold
  idle_timeout                 = var.idle_timeout
  instance_port                = var.instance_port
  lb_port                      = var.lb_port
  lb_protocol                  = var.lb_protocol
  listener_forward             = var.listener_forward
  load_balancer_id             = var.load_balancer_id
  master_slave_server_group_id = var.master_slave_server_group_id
  persistence_timeout          = var.persistence_timeout
  protocol                     = var.protocol
  request_timeout              = var.request_timeout
  scheduler                    = var.scheduler
  server_certificate_id        = var.server_certificate_id
  server_group_id              = var.server_group_id
  ssl_certificate_id           = var.ssl_certificate_id
  sticky_session               = var.sticky_session
  sticky_session_type          = var.sticky_session_type
  tls_cipher_policy            = var.tls_cipher_policy
  unhealthy_threshold          = var.unhealthy_threshold

  dynamic "x_forwarded_for" {
    for_each = var.x_forwarded_for
    content {
      retrive_slb_id    = x_forwarded_for.value["retrive_slb_id"]
      retrive_slb_ip    = x_forwarded_for.value["retrive_slb_ip"]
      retrive_slb_proto = x_forwarded_for.value["retrive_slb_proto"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "health_check_connect_port" {
  description = "returns a number"
  value       = alicloud_slb_listener.this.health_check_connect_port
}

output "health_check_method" {
  description = "returns a string"
  value       = alicloud_slb_listener.this.health_check_method
}

output "id" {
  description = "returns a string"
  value       = alicloud_slb_listener.this.id
}

output "listener_forward" {
  description = "returns a string"
  value       = alicloud_slb_listener.this.listener_forward
}

output "server_certificate_id" {
  description = "returns a string"
  value       = alicloud_slb_listener.this.server_certificate_id
}

output "ssl_certificate_id" {
  description = "returns a string"
  value       = alicloud_slb_listener.this.ssl_certificate_id
}

output "this" {
  value = alicloud_slb_listener.this
}
```

[top](#index)