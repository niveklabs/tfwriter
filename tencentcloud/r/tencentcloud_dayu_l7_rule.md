# tencentcloud_dayu_l7_rule

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
module "tencentcloud_dayu_l7_rule" {
  source = "./modules/tencentcloud/r/tencentcloud_dayu_l7_rule"

  # domain - (required) is a type of string
  domain = null
  # health_check_code - (optional) is a type of number
  health_check_code = null
  # health_check_health_num - (optional) is a type of number
  health_check_health_num = null
  # health_check_interval - (optional) is a type of number
  health_check_interval = null
  # health_check_method - (optional) is a type of string
  health_check_method = null
  # health_check_path - (optional) is a type of string
  health_check_path = null
  # health_check_switch - (optional) is a type of bool
  health_check_switch = null
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
  # source_list - (required) is a type of set of string
  source_list = []
  # source_type - (required) is a type of number
  source_type = null
  # ssl_id - (optional) is a type of string
  ssl_id = null
  # switch - (required) is a type of bool
  switch = null
}
```

[top](#index)

### Variables

```terraform
variable "domain" {
  description = "(required) - Domain that the layer 7 rule works for. Valid string length ranges from 0 to 80."
  type        = string
}

variable "health_check_code" {
  description = "(optional) - HTTP Status Code. The default is `26`. Valid value ranges: [1~31]. `1` means the return value '1xx' is health. `2` means the return value '2xx' is health. `4` means the return value '3xx' is health. `8` means the return value '4xx' is health. `16` means the return value '5xx' is health. If you want multiple return codes to indicate health, need to add the corresponding values."
  type        = number
  default     = null
}

variable "health_check_health_num" {
  description = "(optional) - Health threshold of health check, and the default is `3`. If a success result is returned for the health check 3 consecutive times, indicates that the forwarding is normal. The value range is [2-10]."
  type        = number
  default     = null
}

variable "health_check_interval" {
  description = "(optional) - Interval time of health check. Valid value ranges: [10~60]sec. The default is 15 sec."
  type        = number
  default     = null
}

variable "health_check_method" {
  description = "(optional) - Methods of health check. The default is 'HEAD', the available value are 'HEAD' and 'GET'."
  type        = string
  default     = null
}

variable "health_check_path" {
  description = "(optional) - Path of health check. The default is `/`."
  type        = string
  default     = null
}

variable "health_check_switch" {
  description = "(optional) - Indicates whether health check is enabled. The default is `false`."
  type        = bool
  default     = null
}

variable "health_check_unhealth_num" {
  description = "(optional) - Unhealthy threshold of health check, and the default is `3`. If the unhealthy result is returned 3 consecutive times, indicates that the forwarding is abnormal. The value range is [2-10]."
  type        = number
  default     = null
}

variable "name" {
  description = "(required) - Name of the rule."
  type        = string
}

variable "protocol" {
  description = "(required) - Protocol of the rule. Valid values: `http`, `https`."
  type        = string
}

variable "resource_id" {
  description = "(required) - ID of the resource that the layer 7 rule works for."
  type        = string
}

variable "resource_type" {
  description = "(required) - Type of the resource that the layer 7 rule works for, valid value is `bgpip`."
  type        = string
}

variable "source_list" {
  description = "(required) - Source list of the rule, it can be a set of ip sources or a set of domain sources. The number of items ranges from 1 to 16."
  type        = set(string)
}

variable "source_type" {
  description = "(required) - Source type, `1` for source of host, `2` for source of IP."
  type        = number
}

variable "ssl_id" {
  description = "(optional) - SSL ID, when the `protocol` is `https`, the field should be set with valid SSL id."
  type        = string
  default     = null
}

variable "switch" {
  description = "(required) - Indicate the rule will take effect or not."
  type        = bool
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_dayu_l7_rule" "this" {
  # domain - (required) is a type of string
  domain = var.domain
  # health_check_code - (optional) is a type of number
  health_check_code = var.health_check_code
  # health_check_health_num - (optional) is a type of number
  health_check_health_num = var.health_check_health_num
  # health_check_interval - (optional) is a type of number
  health_check_interval = var.health_check_interval
  # health_check_method - (optional) is a type of string
  health_check_method = var.health_check_method
  # health_check_path - (optional) is a type of string
  health_check_path = var.health_check_path
  # health_check_switch - (optional) is a type of bool
  health_check_switch = var.health_check_switch
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
  # source_list - (required) is a type of set of string
  source_list = var.source_list
  # source_type - (required) is a type of number
  source_type = var.source_type
  # ssl_id - (optional) is a type of string
  ssl_id = var.ssl_id
  # switch - (required) is a type of bool
  switch = var.switch
}
```

[top](#index)

### Outputs

```terraform
output "health_check_code" {
  description = "returns a number"
  value       = tencentcloud_dayu_l7_rule.this.health_check_code
}

output "health_check_health_num" {
  description = "returns a number"
  value       = tencentcloud_dayu_l7_rule.this.health_check_health_num
}

output "health_check_interval" {
  description = "returns a number"
  value       = tencentcloud_dayu_l7_rule.this.health_check_interval
}

output "health_check_method" {
  description = "returns a string"
  value       = tencentcloud_dayu_l7_rule.this.health_check_method
}

output "health_check_path" {
  description = "returns a string"
  value       = tencentcloud_dayu_l7_rule.this.health_check_path
}

output "health_check_switch" {
  description = "returns a bool"
  value       = tencentcloud_dayu_l7_rule.this.health_check_switch
}

output "health_check_unhealth_num" {
  description = "returns a number"
  value       = tencentcloud_dayu_l7_rule.this.health_check_unhealth_num
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_dayu_l7_rule.this.id
}

output "rule_id" {
  description = "returns a string"
  value       = tencentcloud_dayu_l7_rule.this.rule_id
}

output "status" {
  description = "returns a number"
  value       = tencentcloud_dayu_l7_rule.this.status
}

output "this" {
  value = tencentcloud_dayu_l7_rule.this
}
```

[top](#index)