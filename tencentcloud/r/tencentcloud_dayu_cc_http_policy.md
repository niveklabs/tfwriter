# tencentcloud_dayu_cc_http_policy

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
module "tencentcloud_dayu_cc_http_policy" {
  source = "./modules/tencentcloud/r/tencentcloud_dayu_cc_http_policy"

  # action - (optional) is a type of string
  action = null
  # frequency - (optional) is a type of number
  frequency = null
  # ip - (optional) is a type of string
  ip = null
  # name - (required) is a type of string
  name = null
  # resource_id - (required) is a type of string
  resource_id = null
  # resource_type - (required) is a type of string
  resource_type = null
  # smode - (optional) is a type of string
  smode = null
  # switch - (optional) is a type of bool
  switch = null

  rule_list = [{
    operator = null
    skey     = null
    value    = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "action" {
  description = "(optional) - Action mode, only valid when `smode` is `matching`. Valid values are `alg` and `drop`."
  type        = string
  default     = null
}

variable "frequency" {
  description = "(optional) - Max frequency per minute, only valid when `smode` is `speedlimit`, the valid value ranges from 1 to 10000."
  type        = number
  default     = null
}

variable "ip" {
  description = "(optional) - Ip of the CC self-define http policy, only valid when `resource_type` is `bgp-multip`. The num of list items can only be set one."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name of the CC self-define http policy. Length should between 1 and 20."
  type        = string
}

variable "resource_id" {
  description = "(required) - ID of the resource that the CC self-define http policy works for."
  type        = string
}

variable "resource_type" {
  description = "(required) - Type of the resource that the CC self-define http policy works for, valid values are `bgpip`, `bgp`, `bgp-multip` and `net`."
  type        = string
}

variable "smode" {
  description = "(optional) - Match mode, and valid values are `matching`, `speedlimit`. Note: the speed limit type CC self-define policy can only set one."
  type        = string
  default     = null
}

variable "switch" {
  description = "(optional) - Indicate the CC self-define http policy takes effect or not."
  type        = bool
  default     = null
}

variable "rule_list" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      operator = string
      skey     = string
      value    = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_dayu_cc_http_policy" "this" {
  # action - (optional) is a type of string
  action = var.action
  # frequency - (optional) is a type of number
  frequency = var.frequency
  # ip - (optional) is a type of string
  ip = var.ip
  # name - (required) is a type of string
  name = var.name
  # resource_id - (required) is a type of string
  resource_id = var.resource_id
  # resource_type - (required) is a type of string
  resource_type = var.resource_type
  # smode - (optional) is a type of string
  smode = var.smode
  # switch - (optional) is a type of bool
  switch = var.switch

  dynamic "rule_list" {
    for_each = var.rule_list
    content {
      # operator - (optional) is a type of string
      operator = rule_list.value["operator"]
      # skey - (optional) is a type of string
      skey = rule_list.value["skey"]
      # value - (optional) is a type of string
      value = rule_list.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "action" {
  description = "returns a string"
  value       = tencentcloud_dayu_cc_http_policy.this.action
}

output "create_time" {
  description = "returns a string"
  value       = tencentcloud_dayu_cc_http_policy.this.create_time
}

output "frequency" {
  description = "returns a number"
  value       = tencentcloud_dayu_cc_http_policy.this.frequency
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_dayu_cc_http_policy.this.id
}

output "ip" {
  description = "returns a string"
  value       = tencentcloud_dayu_cc_http_policy.this.ip
}

output "policy_id" {
  description = "returns a string"
  value       = tencentcloud_dayu_cc_http_policy.this.policy_id
}

output "this" {
  value = tencentcloud_dayu_cc_http_policy.this
}
```

[top](#index)