# thunder_slb_template_port

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
module "thunder_slb_template_port" {
  source = "./modules/thunder/r/thunder_slb_template_port"

  # add - (optional) is a type of number
  add = null
  # bw_rate_limit - (optional) is a type of number
  bw_rate_limit = null
  # bw_rate_limit_duration - (optional) is a type of number
  bw_rate_limit_duration = null
  # bw_rate_limit_no_logging - (optional) is a type of number
  bw_rate_limit_no_logging = null
  # bw_rate_limit_resume - (optional) is a type of number
  bw_rate_limit_resume = null
  # conn_limit - (optional) is a type of number
  conn_limit = null
  # conn_limit_no_logging - (optional) is a type of number
  conn_limit_no_logging = null
  # conn_rate_limit - (optional) is a type of number
  conn_rate_limit = null
  # conn_rate_limit_no_logging - (optional) is a type of number
  conn_rate_limit_no_logging = null
  # dampening_flaps - (optional) is a type of number
  dampening_flaps = null
  # decrement - (optional) is a type of number
  decrement = null
  # del_session_on_server_down - (optional) is a type of number
  del_session_on_server_down = null
  # dest_nat - (optional) is a type of number
  dest_nat = null
  # down_grace_period - (optional) is a type of number
  down_grace_period = null
  # down_timer - (optional) is a type of number
  down_timer = null
  # dscp - (optional) is a type of number
  dscp = null
  # dynamic_member_priority - (optional) is a type of number
  dynamic_member_priority = null
  # every - (optional) is a type of number
  every = null
  # extended_stats - (optional) is a type of number
  extended_stats = null
  # flap_period - (optional) is a type of number
  flap_period = null
  # health_check - (optional) is a type of string
  health_check = null
  # health_check_disable - (optional) is a type of number
  health_check_disable = null
  # inband_health_check - (optional) is a type of number
  inband_health_check = null
  # initial_slow_start - (optional) is a type of number
  initial_slow_start = null
  # name - (optional) is a type of string
  name = null
  # no_ssl - (optional) is a type of number
  no_ssl = null
  # rate_interval - (optional) is a type of string
  rate_interval = null
  # reassign - (optional) is a type of number
  reassign = null
  # request_rate_interval - (optional) is a type of string
  request_rate_interval = null
  # request_rate_limit - (optional) is a type of number
  request_rate_limit = null
  # request_rate_no_logging - (optional) is a type of number
  request_rate_no_logging = null
  # resel_on_reset - (optional) is a type of number
  resel_on_reset = null
  # reset - (optional) is a type of number
  reset = null
  # restore_svc_time - (optional) is a type of number
  restore_svc_time = null
  # resume - (optional) is a type of number
  resume = null
  # retry - (optional) is a type of number
  retry = null
  # shared_partition_pool - (optional) is a type of number
  shared_partition_pool = null
  # slow_start - (optional) is a type of number
  slow_start = null
  # source_nat - (optional) is a type of string
  source_nat = null
  # stats_data_action - (optional) is a type of string
  stats_data_action = null
  # sub_group - (optional) is a type of number
  sub_group = null
  # template_port_pool_shared - (optional) is a type of string
  template_port_pool_shared = null
  # till - (optional) is a type of number
  till = null
  # times - (optional) is a type of number
  times = null
  # user_tag - (optional) is a type of string
  user_tag = null
  # uuid - (optional) is a type of string
  uuid = null
  # weight - (optional) is a type of number
  weight = null
}
```

[top](#index)

### Variables

```terraform
variable "add" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "bw_rate_limit" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "bw_rate_limit_duration" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "bw_rate_limit_no_logging" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "bw_rate_limit_resume" {
  description = "(optional)"
  type        = number
  default     = null
}

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

variable "dampening_flaps" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "decrement" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "del_session_on_server_down" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dest_nat" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "down_grace_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "down_timer" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dscp" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dynamic_member_priority" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "every" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "extended_stats" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "flap_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "health_check" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "health_check_disable" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "inband_health_check" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "initial_slow_start" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "no_ssl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "rate_interval" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "reassign" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "request_rate_interval" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "request_rate_limit" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "request_rate_no_logging" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "resel_on_reset" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "reset" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "restore_svc_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "resume" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "retry" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "shared_partition_pool" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "slow_start" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "source_nat" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "stats_data_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sub_group" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "template_port_pool_shared" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "till" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "times" {
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

variable "weight" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "thunder_slb_template_port" "this" {
  # add - (optional) is a type of number
  add = var.add
  # bw_rate_limit - (optional) is a type of number
  bw_rate_limit = var.bw_rate_limit
  # bw_rate_limit_duration - (optional) is a type of number
  bw_rate_limit_duration = var.bw_rate_limit_duration
  # bw_rate_limit_no_logging - (optional) is a type of number
  bw_rate_limit_no_logging = var.bw_rate_limit_no_logging
  # bw_rate_limit_resume - (optional) is a type of number
  bw_rate_limit_resume = var.bw_rate_limit_resume
  # conn_limit - (optional) is a type of number
  conn_limit = var.conn_limit
  # conn_limit_no_logging - (optional) is a type of number
  conn_limit_no_logging = var.conn_limit_no_logging
  # conn_rate_limit - (optional) is a type of number
  conn_rate_limit = var.conn_rate_limit
  # conn_rate_limit_no_logging - (optional) is a type of number
  conn_rate_limit_no_logging = var.conn_rate_limit_no_logging
  # dampening_flaps - (optional) is a type of number
  dampening_flaps = var.dampening_flaps
  # decrement - (optional) is a type of number
  decrement = var.decrement
  # del_session_on_server_down - (optional) is a type of number
  del_session_on_server_down = var.del_session_on_server_down
  # dest_nat - (optional) is a type of number
  dest_nat = var.dest_nat
  # down_grace_period - (optional) is a type of number
  down_grace_period = var.down_grace_period
  # down_timer - (optional) is a type of number
  down_timer = var.down_timer
  # dscp - (optional) is a type of number
  dscp = var.dscp
  # dynamic_member_priority - (optional) is a type of number
  dynamic_member_priority = var.dynamic_member_priority
  # every - (optional) is a type of number
  every = var.every
  # extended_stats - (optional) is a type of number
  extended_stats = var.extended_stats
  # flap_period - (optional) is a type of number
  flap_period = var.flap_period
  # health_check - (optional) is a type of string
  health_check = var.health_check
  # health_check_disable - (optional) is a type of number
  health_check_disable = var.health_check_disable
  # inband_health_check - (optional) is a type of number
  inband_health_check = var.inband_health_check
  # initial_slow_start - (optional) is a type of number
  initial_slow_start = var.initial_slow_start
  # name - (optional) is a type of string
  name = var.name
  # no_ssl - (optional) is a type of number
  no_ssl = var.no_ssl
  # rate_interval - (optional) is a type of string
  rate_interval = var.rate_interval
  # reassign - (optional) is a type of number
  reassign = var.reassign
  # request_rate_interval - (optional) is a type of string
  request_rate_interval = var.request_rate_interval
  # request_rate_limit - (optional) is a type of number
  request_rate_limit = var.request_rate_limit
  # request_rate_no_logging - (optional) is a type of number
  request_rate_no_logging = var.request_rate_no_logging
  # resel_on_reset - (optional) is a type of number
  resel_on_reset = var.resel_on_reset
  # reset - (optional) is a type of number
  reset = var.reset
  # restore_svc_time - (optional) is a type of number
  restore_svc_time = var.restore_svc_time
  # resume - (optional) is a type of number
  resume = var.resume
  # retry - (optional) is a type of number
  retry = var.retry
  # shared_partition_pool - (optional) is a type of number
  shared_partition_pool = var.shared_partition_pool
  # slow_start - (optional) is a type of number
  slow_start = var.slow_start
  # source_nat - (optional) is a type of string
  source_nat = var.source_nat
  # stats_data_action - (optional) is a type of string
  stats_data_action = var.stats_data_action
  # sub_group - (optional) is a type of number
  sub_group = var.sub_group
  # template_port_pool_shared - (optional) is a type of string
  template_port_pool_shared = var.template_port_pool_shared
  # till - (optional) is a type of number
  till = var.till
  # times - (optional) is a type of number
  times = var.times
  # user_tag - (optional) is a type of string
  user_tag = var.user_tag
  # uuid - (optional) is a type of string
  uuid = var.uuid
  # weight - (optional) is a type of number
  weight = var.weight
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_slb_template_port.this.id
}

output "this" {
  value = thunder_slb_template_port.this
}
```

[top](#index)