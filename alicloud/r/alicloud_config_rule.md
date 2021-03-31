# alicloud_config_rule

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
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_config_rule" {
  source = "./modules/alicloud/r/alicloud_config_rule"

  # description - (optional) is a type of string
  description = null
  # input_parameters - (optional) is a type of map of string
  input_parameters = {}
  # member_id - (optional) is a type of number
  member_id = null
  # multi_account - (optional) is a type of bool
  multi_account = null
  # risk_level - (required) is a type of number
  risk_level = null
  # rule_name - (required) is a type of string
  rule_name = null
  # scope_compliance_resource_id - (optional) is a type of string
  scope_compliance_resource_id = null
  # scope_compliance_resource_types - (required) is a type of set of string
  scope_compliance_resource_types = []
  # source_detail_message_type - (required) is a type of string
  source_detail_message_type = null
  # source_identifier - (required) is a type of string
  source_identifier = null
  # source_maximum_execution_frequency - (optional) is a type of string
  source_maximum_execution_frequency = null
  # source_owner - (required) is a type of string
  source_owner = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "input_parameters" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "member_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "multi_account" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "risk_level" {
  description = "(required)"
  type        = number
}

variable "rule_name" {
  description = "(required)"
  type        = string
}

variable "scope_compliance_resource_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scope_compliance_resource_types" {
  description = "(required)"
  type        = set(string)
}

variable "source_detail_message_type" {
  description = "(required)"
  type        = string
}

variable "source_identifier" {
  description = "(required)"
  type        = string
}

variable "source_maximum_execution_frequency" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_owner" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_config_rule" "this" {
  description                        = var.description
  input_parameters                   = var.input_parameters
  member_id                          = var.member_id
  multi_account                      = var.multi_account
  risk_level                         = var.risk_level
  rule_name                          = var.rule_name
  scope_compliance_resource_id       = var.scope_compliance_resource_id
  scope_compliance_resource_types    = var.scope_compliance_resource_types
  source_detail_message_type         = var.source_detail_message_type
  source_identifier                  = var.source_identifier
  source_maximum_execution_frequency = var.source_maximum_execution_frequency
  source_owner                       = var.source_owner
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_config_rule.this.id
}

output "this" {
  value = alicloud_config_rule.this
}
```

[top](#index)