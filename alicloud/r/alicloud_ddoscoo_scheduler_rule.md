# alicloud_ddoscoo_scheduler_rule

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
module "alicloud_ddoscoo_scheduler_rule" {
  source = "./modules/alicloud/r/alicloud_ddoscoo_scheduler_rule"

  # param - (optional) is a type of string
  param = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # rule_name - (required) is a type of string
  rule_name = null
  # rule_type - (required) is a type of number
  rule_type = null

  rules = [{
    priority   = null
    region_id  = null
    status     = null
    type       = null
    value      = null
    value_type = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "param" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rule_name" {
  description = "(required)"
  type        = string
}

variable "rule_type" {
  description = "(required)"
  type        = number
}

variable "rules" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      priority   = number
      region_id  = string
      status     = number
      type       = string
      value      = string
      value_type = number
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_ddoscoo_scheduler_rule" "this" {
  # param - (optional) is a type of string
  param = var.param
  # resource_group_id - (optional) is a type of string
  resource_group_id = var.resource_group_id
  # rule_name - (required) is a type of string
  rule_name = var.rule_name
  # rule_type - (required) is a type of number
  rule_type = var.rule_type

  dynamic "rules" {
    for_each = var.rules
    content {
      # priority - (optional) is a type of number
      priority = rules.value["priority"]
      # region_id - (optional) is a type of string
      region_id = rules.value["region_id"]
      # type - (optional) is a type of string
      type = rules.value["type"]
      # value - (optional) is a type of string
      value = rules.value["value"]
      # value_type - (optional) is a type of number
      value_type = rules.value["value_type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cname" {
  description = "returns a string"
  value       = alicloud_ddoscoo_scheduler_rule.this.cname
}

output "id" {
  description = "returns a string"
  value       = alicloud_ddoscoo_scheduler_rule.this.id
}

output "this" {
  value = alicloud_ddoscoo_scheduler_rule.this
}
```

[top](#index)