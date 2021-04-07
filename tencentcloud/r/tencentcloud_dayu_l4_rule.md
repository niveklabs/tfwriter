# tencentcloud_dayu_l4_rule

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tencentcloud = ">= 1.56.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tencentcloud_dayu_l4_rule" {
  source = "./modules/tencentcloud/r/tencentcloud_dayu_l4_rule"

  # d_port - (required) is a type of number
  d_port = null
  # health_check_health_num - (optional) is a type of number
  health_check_health_num = null
  # health_check_interval - (optional) is a type of number
  health_check_interval = null
  # health_check_switch - (optional) is a type of bool
  health_check_switch = null
  # health_check_timeout - (optional) is a type of number
  health_check_timeout = null
  # health_check_unhealth_num - (optional) is a type of number
  health_check_unhealth_num = null
  # name - (required) is a type of string
  name = null
  # protocol - (required) is a type of string
  protocol = null
  # resource_id - (required) is a type of string
  resource_id = null
  # resource_type - (required) is a type of string
  resource_type = null
  # s_port - (required) is a type of number
  s_port = null
  # session_switch - (optional) is a type of bool
  session_switch = null
  # session_time - (optional) is a type of number
  session_time = null
  # source_type - (required) is a type of number
  source_type = null

  source_list = [{
    source = null
    weight = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "d_port" {
  description = "(required) - The destination port of the L4 rule."
  type        = number
}

variable "health_check_health_num" {
  description = "(optional) - Health threshold of health check, and the default is 3. If a success result is returned for the health check 3 consecutive times, indicates that the forwarding is normal. The value range is 2-10."
  type        = number
  default     = null
}

variable "health_check_interval" {
  description = "(optional) - Interval time of health check. The value range is 10-60 sec, and the default is 15 sec."
  type        = number
  default     = null
}

variable "health_check_switch" {
  description = "(optional) - Indicates whether health check is enabled. The default is `false`. Only valid when source list has more than one source item."
  type        = bool
  default     = null
}

variable "health_check_timeout" {
  description = "(optional) - HTTP Status Code. The default is 26 and value range is 2-60."
  type        = number
  default     = null
}

variable "health_check_unhealth_num" {
  description = "(optional) - Unhealthy threshold of health check, and the default is 3. If the unhealthy result is returned 3 consecutive times, indicates that the forwarding is abnormal. The value range is 2-10."
  type        = number
  default     = null
}

variable "name" {
  description = "(required) - Name of the rule. When the `resource_type` is `net`, this field should be set with valid domain."
  type        = string
}

variable "protocol" {
  description = "(required) - Protocol of the rule. Valid values: `http`, `https`. When `source_type` is 1(host source), the value of this field can only set with `tcp`."
  type        = string
}

variable "resource_id" {
  description = "(required) - ID of the resource that the layer 4 rule works for."
  type        = string
}

variable "resource_type" {
  description = "(required) - Type of the resource that the layer 4 rule works for. Valid values: `bgpip` and `net`."
  type        = string
}

variable "s_port" {
  description = "(required) - The source port of the L4 rule."
  type        = number
}

variable "session_switch" {
  description = "(optional) - Indicate that the session will keep or not, and default value is `false`."
  type        = bool
  default     = null
}

variable "session_time" {
  description = "(optional) - Session keep time, only valid when `session_switch` is true, the available value ranges from 1 to 300 and unit is second."
  type        = number
  default     = null
}

variable "source_type" {
  description = "(required) - Source type, `1` for source of host, `2` for source of IP."
  type        = number
}

variable "source_list" {
  description = "nested block: NestingSet, min items: 1, max items: 20"
  type = set(object(
    {
      source = string
      weight = number
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_dayu_l4_rule" "this" {
  # d_port - (required) is a type of number
  d_port = var.d_port
  # health_check_health_num - (optional) is a type of number
  health_check_health_num = var.health_check_health_num
  # health_check_interval - (optional) is a type of number
  health_check_interval = var.health_check_interval
  # health_check_switch - (optional) is a type of bool
  health_check_switch = var.health_check_switch
  # health_check_timeout - (optional) is a type of number
  health_check_timeout = var.health_check_timeout
  # health_check_unhealth_num - (optional) is a type of number
  health_check_unhealth_num = var.health_check_unhealth_num
  # name - (required) is a type of string
  name = var.name
  # protocol - (required) is a type of string
  protocol = var.protocol
  # resource_id - (required) is a type of string
  resource_id = var.resource_id
  # resource_type - (required) is a type of string
  resource_type = var.resource_type
  # s_port - (required) is a type of number
  s_port = var.s_port
  # session_switch - (optional) is a type of bool
  session_switch = var.session_switch
  # session_time - (optional) is a type of number
  session_time = var.session_time
  # source_type - (required) is a type of number
  source_type = var.source_type

  dynamic "source_list" {
    for_each = var.source_list
    content {
      # source - (required) is a type of string
      source = source_list.value["source"]
      # weight - (required) is a type of number
      weight = source_list.value["weight"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "health_check_health_num" {
  description = "returns a number"
  value       = tencentcloud_dayu_l4_rule.this.health_check_health_num
}

output "health_check_interval" {
  description = "returns a number"
  value       = tencentcloud_dayu_l4_rule.this.health_check_interval
}

output "health_check_switch" {
  description = "returns a bool"
  value       = tencentcloud_dayu_l4_rule.this.health_check_switch
}

output "health_check_timeout" {
  description = "returns a number"
  value       = tencentcloud_dayu_l4_rule.this.health_check_timeout
}

output "health_check_unhealth_num" {
  description = "returns a number"
  value       = tencentcloud_dayu_l4_rule.this.health_check_unhealth_num
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_dayu_l4_rule.this.id
}

output "lb_type" {
  description = "returns a number"
  value       = tencentcloud_dayu_l4_rule.this.lb_type
}

output "rule_id" {
  description = "returns a string"
  value       = tencentcloud_dayu_l4_rule.this.rule_id
}

output "session_time" {
  description = "returns a number"
  value       = tencentcloud_dayu_l4_rule.this.session_time
}

output "this" {
  value = tencentcloud_dayu_l4_rule.this
}
```

[top](#index)