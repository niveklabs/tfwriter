# alicloud_config_rules

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
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_config_rules" {
  source = "./modules/alicloud/d/alicloud_config_rules"

  # config_rule_state - (optional) is a type of string
  config_rule_state = null
  # enable_details - (optional) is a type of bool
  enable_details = null
  # ids - (optional) is a type of list of string
  ids = []
  # member_id - (optional) is a type of number
  member_id = null
  # message_type - (optional) is a type of string
  message_type = null
  # multi_account - (optional) is a type of bool
  multi_account = null
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # risk_level - (optional) is a type of number
  risk_level = null
}
```

[top](#index)

### Variables

```terraform
variable "config_rule_state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable_details" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "member_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "message_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "multi_account" {
  description = "(optional)"
  type        = bool
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

variable "risk_level" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_config_rules" "this" {
  config_rule_state = var.config_rule_state
  enable_details    = var.enable_details
  ids               = var.ids
  member_id         = var.member_id
  message_type      = var.message_type
  multi_account     = var.multi_account
  name_regex        = var.name_regex
  output_file       = var.output_file
  risk_level        = var.risk_level
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_config_rules.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_config_rules.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_config_rules.this.names
}

output "rules" {
  description = "returns a list of object"
  value       = data.alicloud_config_rules.this.rules
}

output "this" {
  value = alicloud_config_rules.this
}
```

[top](#index)