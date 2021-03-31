# alicloud_cms_monitor_groups

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
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_cms_monitor_groups" {
  source = "./modules/alicloud/d/alicloud_cms_monitor_groups"

  # dynamic_tag_rule_id - (optional) is a type of string
  dynamic_tag_rule_id = null
  # ids - (optional) is a type of list of string
  ids = []
  # include_template_history - (optional) is a type of bool
  include_template_history = null
  # keyword - (optional) is a type of string
  keyword = null
  # monitor_group_name - (optional) is a type of string
  monitor_group_name = null
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # select_contact_groups - (optional) is a type of bool
  select_contact_groups = null
  # tags - (optional) is a type of map of string
  tags = {}
  # type - (optional) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "dynamic_tag_rule_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "include_template_history" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "keyword" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "monitor_group_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "select_contact_groups" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_cms_monitor_groups" "this" {
  dynamic_tag_rule_id      = var.dynamic_tag_rule_id
  ids                      = var.ids
  include_template_history = var.include_template_history
  keyword                  = var.keyword
  monitor_group_name       = var.monitor_group_name
  name_regex               = var.name_regex
  output_file              = var.output_file
  select_contact_groups    = var.select_contact_groups
  tags                     = var.tags
  type                     = var.type
}
```

[top](#index)

### Outputs

```terraform
output "groups" {
  description = "returns a list of object"
  value       = data.alicloud_cms_monitor_groups.this.groups
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_cms_monitor_groups.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_cms_monitor_groups.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_cms_monitor_groups.this.names
}

output "this" {
  value = alicloud_cms_monitor_groups.this
}
```

[top](#index)