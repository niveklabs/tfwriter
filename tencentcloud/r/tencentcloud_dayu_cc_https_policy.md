# tencentcloud_dayu_cc_https_policy

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
module "tencentcloud_dayu_cc_https_policy" {
  source = "./modules/tencentcloud/r/tencentcloud_dayu_cc_https_policy"

  # action - (optional) is a type of string
  action = null
  # domain - (required) is a type of string
  domain = null
  # name - (required) is a type of string
  name = null
  # resource_id - (required) is a type of string
  resource_id = null
  # resource_type - (required) is a type of string
  resource_type = null
  # rule_id - (required) is a type of string
  rule_id = null
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
  description = "(optional) - Action mode. Valid values are `alg` and `drop`."
  type        = string
  default     = null
}

variable "domain" {
  description = "(required) - Domain that the CC self-define https policy works for, only valid when `protocol` is `https`."
  type        = string
}

variable "name" {
  description = "(required) - Name of the CC self-define https policy. Length should between 1 and 20."
  type        = string
}

variable "resource_id" {
  description = "(required) - ID of the resource that the CC self-define https policy works for."
  type        = string
}

variable "resource_type" {
  description = "(required) - Type of the resource that the CC self-define https policy works for, valid value is `bgpip`."
  type        = string
}

variable "rule_id" {
  description = "(required) - Rule id of the domain that the CC self-define https policy works for, only valid when `protocol` is `https`."
  type        = string
}

variable "switch" {
  description = "(optional) - Indicate the CC self-define https policy takes effect or not."
  type        = bool
  default     = null
}

variable "rule_list" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      operator = string
      skey     = string
      value    = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_dayu_cc_https_policy" "this" {
  action        = var.action
  domain        = var.domain
  name          = var.name
  resource_id   = var.resource_id
  resource_type = var.resource_type
  rule_id       = var.rule_id
  switch        = var.switch

  dynamic "rule_list" {
    for_each = var.rule_list
    content {
      operator = rule_list.value["operator"]
      skey     = rule_list.value["skey"]
      value    = rule_list.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "action" {
  description = "returns a string"
  value       = tencentcloud_dayu_cc_https_policy.this.action
}

output "create_time" {
  description = "returns a string"
  value       = tencentcloud_dayu_cc_https_policy.this.create_time
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_dayu_cc_https_policy.this.id
}

output "ip_list" {
  description = "returns a set of string"
  value       = tencentcloud_dayu_cc_https_policy.this.ip_list
}

output "policy_id" {
  description = "returns a string"
  value       = tencentcloud_dayu_cc_https_policy.this.policy_id
}

output "this" {
  value = tencentcloud_dayu_cc_https_policy.this
}
```

[top](#index)