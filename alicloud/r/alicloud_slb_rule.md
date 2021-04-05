# alicloud_slb_rule

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
module "alicloud_slb_rule" {
  source = "./modules/alicloud/r/alicloud_slb_rule"

  # cookie - (optional) is a type of string
  cookie = null
  # cookie_timeout - (optional) is a type of number
  cookie_timeout = null
  # delete_protection_validation - (optional) is a type of bool
  delete_protection_validation = null
  # domain - (optional) is a type of string
  domain = null
  # frontend_port - (required) is a type of number
  frontend_port = null
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
  # health_check_timeout - (optional) is a type of number
  health_check_timeout = null
  # health_check_uri - (optional) is a type of string
  health_check_uri = null
  # healthy_threshold - (optional) is a type of number
  healthy_threshold = null
  # listener_sync - (optional) is a type of string
  listener_sync = null
  # load_balancer_id - (required) is a type of string
  load_balancer_id = null
  # name - (optional) is a type of string
  name = null
  # scheduler - (optional) is a type of string
  scheduler = null
  # server_group_id - (required) is a type of string
  server_group_id = null
  # sticky_session - (optional) is a type of string
  sticky_session = null
  # sticky_session_type - (optional) is a type of string
  sticky_session_type = null
  # unhealthy_threshold - (optional) is a type of number
  unhealthy_threshold = null
  # url - (optional) is a type of string
  url = null
}
```

[top](#index)

### Variables

```terraform
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

variable "domain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "frontend_port" {
  description = "(required)"
  type        = number
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

variable "health_check_timeout" {
  description = "(optional)"
  type        = number
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

variable "listener_sync" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "load_balancer_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scheduler" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server_group_id" {
  description = "(required)"
  type        = string
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

variable "unhealthy_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "url" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_slb_rule" "this" {
  cookie                       = var.cookie
  cookie_timeout               = var.cookie_timeout
  delete_protection_validation = var.delete_protection_validation
  domain                       = var.domain
  frontend_port                = var.frontend_port
  health_check                 = var.health_check
  health_check_connect_port    = var.health_check_connect_port
  health_check_domain          = var.health_check_domain
  health_check_http_code       = var.health_check_http_code
  health_check_interval        = var.health_check_interval
  health_check_timeout         = var.health_check_timeout
  health_check_uri             = var.health_check_uri
  healthy_threshold            = var.healthy_threshold
  listener_sync                = var.listener_sync
  load_balancer_id             = var.load_balancer_id
  name                         = var.name
  scheduler                    = var.scheduler
  server_group_id              = var.server_group_id
  sticky_session               = var.sticky_session
  sticky_session_type          = var.sticky_session_type
  unhealthy_threshold          = var.unhealthy_threshold
  url                          = var.url
}
```

[top](#index)

### Outputs

```terraform
output "health_check_connect_port" {
  description = "returns a number"
  value       = alicloud_slb_rule.this.health_check_connect_port
}

output "id" {
  description = "returns a string"
  value       = alicloud_slb_rule.this.id
}

output "this" {
  value = alicloud_slb_rule.this
}
```

[top](#index)