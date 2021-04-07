# thunder_slb_template_server

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
module "thunder_slb_template_server" {
  source = "./modules/thunder/r/thunder_slb_template_server"

  # add - (optional) is a type of number
  add = null
  # bw_rate_limit - (optional) is a type of number
  bw_rate_limit = null
  # bw_rate_limit_acct - (optional) is a type of string
  bw_rate_limit_acct = null
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
  # dns_query_interval - (optional) is a type of number
  dns_query_interval = null
  # dynamic_server_prefix - (optional) is a type of string
  dynamic_server_prefix = null
  # every - (optional) is a type of number
  every = null
  # extended_stats - (optional) is a type of number
  extended_stats = null
  # health_check - (optional) is a type of string
  health_check = null
  # health_check_disable - (optional) is a type of number
  health_check_disable = null
  # initial_slow_start - (optional) is a type of number
  initial_slow_start = null
  # log_selection_failure - (optional) is a type of number
  log_selection_failure = null
  # max_dynamic_server - (optional) is a type of number
  max_dynamic_server = null
  # min_ttl_ratio - (optional) is a type of number
  min_ttl_ratio = null
  # name - (optional) is a type of string
  name = null
  # rate_interval - (optional) is a type of string
  rate_interval = null
  # resume - (optional) is a type of number
  resume = null
  # slow_start - (optional) is a type of number
  slow_start = null
  # spoofing_cache - (optional) is a type of number
  spoofing_cache = null
  # stats_data_action - (optional) is a type of string
  stats_data_action = null
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

variable "bw_rate_limit_acct" {
  description = "(optional)"
  type        = string
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

variable "dns_query_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dynamic_server_prefix" {
  description = "(optional)"
  type        = string
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

variable "initial_slow_start" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "log_selection_failure" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_dynamic_server" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "min_ttl_ratio" {
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

variable "resume" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "slow_start" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "spoofing_cache" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "stats_data_action" {
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
resource "thunder_slb_template_server" "this" {
  # add - (optional) is a type of number
  add = var.add
  # bw_rate_limit - (optional) is a type of number
  bw_rate_limit = var.bw_rate_limit
  # bw_rate_limit_acct - (optional) is a type of string
  bw_rate_limit_acct = var.bw_rate_limit_acct
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
  # dns_query_interval - (optional) is a type of number
  dns_query_interval = var.dns_query_interval
  # dynamic_server_prefix - (optional) is a type of string
  dynamic_server_prefix = var.dynamic_server_prefix
  # every - (optional) is a type of number
  every = var.every
  # extended_stats - (optional) is a type of number
  extended_stats = var.extended_stats
  # health_check - (optional) is a type of string
  health_check = var.health_check
  # health_check_disable - (optional) is a type of number
  health_check_disable = var.health_check_disable
  # initial_slow_start - (optional) is a type of number
  initial_slow_start = var.initial_slow_start
  # log_selection_failure - (optional) is a type of number
  log_selection_failure = var.log_selection_failure
  # max_dynamic_server - (optional) is a type of number
  max_dynamic_server = var.max_dynamic_server
  # min_ttl_ratio - (optional) is a type of number
  min_ttl_ratio = var.min_ttl_ratio
  # name - (optional) is a type of string
  name = var.name
  # rate_interval - (optional) is a type of string
  rate_interval = var.rate_interval
  # resume - (optional) is a type of number
  resume = var.resume
  # slow_start - (optional) is a type of number
  slow_start = var.slow_start
  # spoofing_cache - (optional) is a type of number
  spoofing_cache = var.spoofing_cache
  # stats_data_action - (optional) is a type of string
  stats_data_action = var.stats_data_action
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
  value       = thunder_slb_template_server.this.id
}

output "this" {
  value = thunder_slb_template_server.this
}
```

[top](#index)