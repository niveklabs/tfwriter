# checkpoint_management_data_https_rule

[back](../checkpoint.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    checkpoint = ">= 1.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "checkpoint_management_data_https_rule" {
  source = "./modules/checkpoint/d/checkpoint_management_data_https_rule"

  # layer - (required) is a type of string
  layer = null
  # rule_number - (optional) is a type of string
  rule_number = null
  # uid - (optional) is a type of string
  uid = null
}
```

[top](#index)

### Variables

```terraform
variable "layer" {
  description = "(required) - Layer that holds the Object. Identified by the Name or UID."
  type        = string
}

variable "rule_number" {
  description = "(optional) - HTTPS rule number."
  type        = string
  default     = null
}

variable "uid" {
  description = "(optional) - Object unique identifier."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "checkpoint_management_data_https_rule" "this" {
  layer       = var.layer
  rule_number = var.rule_number
  uid         = var.uid
}
```

[top](#index)

### Outputs

```terraform
output "action" {
  description = "returns a string"
  value       = data.checkpoint_management_data_https_rule.this.action
}

output "blade" {
  description = "returns a set of string"
  value       = data.checkpoint_management_data_https_rule.this.blade
}

output "certificate" {
  description = "returns a string"
  value       = data.checkpoint_management_data_https_rule.this.certificate
}

output "comments" {
  description = "returns a string"
  value       = data.checkpoint_management_data_https_rule.this.comments
}

output "destination" {
  description = "returns a set of string"
  value       = data.checkpoint_management_data_https_rule.this.destination
}

output "destination_negate" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_https_rule.this.destination_negate
}

output "enabled" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_https_rule.this.enabled
}

output "id" {
  description = "returns a string"
  value       = data.checkpoint_management_data_https_rule.this.id
}

output "install_on" {
  description = "returns a set of string"
  value       = data.checkpoint_management_data_https_rule.this.install_on
}

output "name" {
  description = "returns a string"
  value       = data.checkpoint_management_data_https_rule.this.name
}

output "service" {
  description = "returns a set of string"
  value       = data.checkpoint_management_data_https_rule.this.service
}

output "service_negate" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_https_rule.this.service_negate
}

output "site_category" {
  description = "returns a set of string"
  value       = data.checkpoint_management_data_https_rule.this.site_category
}

output "site_category_negate" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_https_rule.this.site_category_negate
}

output "source" {
  description = "returns a set of string"
  value       = data.checkpoint_management_data_https_rule.this.source
}

output "source_negate" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_https_rule.this.source_negate
}

output "track" {
  description = "returns a string"
  value       = data.checkpoint_management_data_https_rule.this.track
}

output "this" {
  value = checkpoint_management_data_https_rule.this
}
```

[top](#index)