# alicloud_cms_group_metric_rules

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_cms_group_metric_rules" {
  source = "./modules/alicloud/d/alicloud_cms_group_metric_rules"

  # dimensions - (optional) is a type of string
  dimensions = null
  # enable_state - (optional) is a type of bool
  enable_state = null
  # group_id - (optional) is a type of string
  group_id = null
  # group_metric_rule_name - (optional) is a type of string
  group_metric_rule_name = null
  # ids - (optional) is a type of list of string
  ids = []
  # metric_name - (optional) is a type of string
  metric_name = null
  # name_regex - (optional) is a type of string
  name_regex = null
  # namespace - (optional) is a type of string
  namespace = null
  # output_file - (optional) is a type of string
  output_file = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "dimensions" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable_state" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group_metric_rule_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "metric_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "namespace" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_cms_group_metric_rules" "this" {
  dimensions             = var.dimensions
  enable_state           = var.enable_state
  group_id               = var.group_id
  group_metric_rule_name = var.group_metric_rule_name
  ids                    = var.ids
  metric_name            = var.metric_name
  name_regex             = var.name_regex
  namespace              = var.namespace
  output_file            = var.output_file
  status                 = var.status
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_cms_group_metric_rules.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_cms_group_metric_rules.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_cms_group_metric_rules.this.names
}

output "rules" {
  description = "returns a list of object"
  value       = data.alicloud_cms_group_metric_rules.this.rules
}

output "this" {
  value = alicloud_cms_group_metric_rules.this
}
```

[top](#index)