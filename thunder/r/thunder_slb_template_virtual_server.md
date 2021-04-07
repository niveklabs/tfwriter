# thunder_slb_template_virtual_server

[back](../thunder.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    thunder = ">= 0.4.16"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "thunder_slb_template_virtual_server" {
  source = "./modules/thunder/r/thunder_slb_template_virtual_server"

  # conn_limit - (optional) is a type of number
  conn_limit = null
  # conn_limit_no_logging - (optional) is a type of number
  conn_limit_no_logging = null
  # conn_limit_reset - (optional) is a type of number
  conn_limit_reset = null
  # conn_rate_limit - (optional) is a type of number
  conn_rate_limit = null
  # conn_rate_limit_no_logging - (optional) is a type of number
  conn_rate_limit_no_logging = null
  # conn_rate_limit_reset - (optional) is a type of number
  conn_rate_limit_reset = null
  # icmp_lockup - (optional) is a type of number
  icmp_lockup = null
  # icmp_lockup_period - (optional) is a type of number
  icmp_lockup_period = null
  # icmp_rate_limit - (optional) is a type of number
  icmp_rate_limit = null
  # icmpv6_lockup - (optional) is a type of number
  icmpv6_lockup = null
  # icmpv6_lockup_period - (optional) is a type of number
  icmpv6_lockup_period = null
  # icmpv6_rate_limit - (optional) is a type of number
  icmpv6_rate_limit = null
  # name - (optional) is a type of string
  name = null
  # rate_interval - (optional) is a type of string
  rate_interval = null
  # subnet_gratuitous_arp - (optional) is a type of number
  subnet_gratuitous_arp = null
  # tcp_stack_tfo_active_conn_limit - (optional) is a type of number
  tcp_stack_tfo_active_conn_limit = null
  # tcp_stack_tfo_backoff_time - (optional) is a type of number
  tcp_stack_tfo_backoff_time = null
  # tcp_stack_tfo_cookie_time_limit - (optional) is a type of number
  tcp_stack_tfo_cookie_time_limit = null
  # user_tag - (optional) is a type of string
  user_tag = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "conn_limit" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "conn_limit_no_logging" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "conn_limit_reset" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "conn_rate_limit" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "conn_rate_limit_no_logging" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "conn_rate_limit_reset" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "icmp_lockup" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "icmp_lockup_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "icmp_rate_limit" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "icmpv6_lockup" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "icmpv6_lockup_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "icmpv6_rate_limit" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rate_interval" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subnet_gratuitous_arp" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tcp_stack_tfo_active_conn_limit" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tcp_stack_tfo_backoff_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tcp_stack_tfo_cookie_time_limit" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "user_tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "thunder_slb_template_virtual_server" "this" {
  # conn_limit - (optional) is a type of number
  conn_limit = var.conn_limit
  # conn_limit_no_logging - (optional) is a type of number
  conn_limit_no_logging = var.conn_limit_no_logging
  # conn_limit_reset - (optional) is a type of number
  conn_limit_reset = var.conn_limit_reset
  # conn_rate_limit - (optional) is a type of number
  conn_rate_limit = var.conn_rate_limit
  # conn_rate_limit_no_logging - (optional) is a type of number
  conn_rate_limit_no_logging = var.conn_rate_limit_no_logging
  # conn_rate_limit_reset - (optional) is a type of number
  conn_rate_limit_reset = var.conn_rate_limit_reset
  # icmp_lockup - (optional) is a type of number
  icmp_lockup = var.icmp_lockup
  # icmp_lockup_period - (optional) is a type of number
  icmp_lockup_period = var.icmp_lockup_period
  # icmp_rate_limit - (optional) is a type of number
  icmp_rate_limit = var.icmp_rate_limit
  # icmpv6_lockup - (optional) is a type of number
  icmpv6_lockup = var.icmpv6_lockup
  # icmpv6_lockup_period - (optional) is a type of number
  icmpv6_lockup_period = var.icmpv6_lockup_period
  # icmpv6_rate_limit - (optional) is a type of number
  icmpv6_rate_limit = var.icmpv6_rate_limit
  # name - (optional) is a type of string
  name = var.name
  # rate_interval - (optional) is a type of string
  rate_interval = var.rate_interval
  # subnet_gratuitous_arp - (optional) is a type of number
  subnet_gratuitous_arp = var.subnet_gratuitous_arp
  # tcp_stack_tfo_active_conn_limit - (optional) is a type of number
  tcp_stack_tfo_active_conn_limit = var.tcp_stack_tfo_active_conn_limit
  # tcp_stack_tfo_backoff_time - (optional) is a type of number
  tcp_stack_tfo_backoff_time = var.tcp_stack_tfo_backoff_time
  # tcp_stack_tfo_cookie_time_limit - (optional) is a type of number
  tcp_stack_tfo_cookie_time_limit = var.tcp_stack_tfo_cookie_time_limit
  # user_tag - (optional) is a type of string
  user_tag = var.user_tag
  # uuid - (optional) is a type of string
  uuid = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_slb_template_virtual_server.this.id
}

output "this" {
  value = thunder_slb_template_virtual_server.this
}
```

[top](#index)