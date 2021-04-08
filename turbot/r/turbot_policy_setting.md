# turbot_policy_setting

[back](../turbot.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    turbot = ">= 1.8.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "turbot_policy_setting" {
  source = "./modules/turbot/r/turbot_policy_setting"

  # note - (optional) is a type of string
  note = null
  # pgp_key - (optional) is a type of string
  pgp_key = null
  # precedence - (optional) is a type of string
  precedence = null
  # resource - (required) is a type of string
  resource = null
  # template - (optional) is a type of string
  template = null
  # template_input - (optional) is a type of string
  template_input = null
  # type - (required) is a type of string
  type = null
  # valid_from_timestamp - (optional) is a type of string
  valid_from_timestamp = null
  # valid_to_timestamp - (optional) is a type of string
  valid_to_timestamp = null
  # value - (optional) is a type of string
  value = null
}
```

[top](#index)

### Variables

```terraform
variable "note" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pgp_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "precedence" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource" {
  description = "(required)"
  type        = string
}

variable "template" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_input" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "valid_from_timestamp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "valid_to_timestamp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "value" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "turbot_policy_setting" "this" {
  # note - (optional) is a type of string
  note = var.note
  # pgp_key - (optional) is a type of string
  pgp_key = var.pgp_key
  # precedence - (optional) is a type of string
  precedence = var.precedence
  # resource - (required) is a type of string
  resource = var.resource
  # template - (optional) is a type of string
  template = var.template
  # template_input - (optional) is a type of string
  template_input = var.template_input
  # type - (required) is a type of string
  type = var.type
  # valid_from_timestamp - (optional) is a type of string
  valid_from_timestamp = var.valid_from_timestamp
  # valid_to_timestamp - (optional) is a type of string
  valid_to_timestamp = var.valid_to_timestamp
  # value - (optional) is a type of string
  value = var.value
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = turbot_policy_setting.this.id
}

output "resource_akas" {
  description = "returns a list of string"
  value       = turbot_policy_setting.this.resource_akas
}

output "value_key_fingerprint" {
  description = "returns a string"
  value       = turbot_policy_setting.this.value_key_fingerprint
}

output "value_source" {
  description = "returns a string"
  value       = turbot_policy_setting.this.value_source
}

output "value_source_key_fingerprint" {
  description = "returns a string"
  value       = turbot_policy_setting.this.value_source_key_fingerprint
}

output "value_source_used" {
  description = "returns a bool"
  value       = turbot_policy_setting.this.value_source_used
}

output "this" {
  value = turbot_policy_setting.this
}
```

[top](#index)