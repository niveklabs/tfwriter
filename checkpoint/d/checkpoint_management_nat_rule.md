# checkpoint_management_nat_rule

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
module "checkpoint_management_nat_rule" {
  source = "./modules/checkpoint/d/checkpoint_management_nat_rule"

  # name - (optional) is a type of string
  name = null
  # package - (required) is a type of string
  package = null
  # uid - (optional) is a type of string
  uid = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - Rule name."
  type        = string
  default     = null
}

variable "package" {
  description = "(required) - Name of the package."
  type        = string
}

variable "uid" {
  description = "(optional) - Rule UID."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "checkpoint_management_nat_rule" "this" {
  name    = var.name
  package = var.package
  uid     = var.uid
}
```

[top](#index)

### Outputs

```terraform
output "auto_generated" {
  description = "returns a bool"
  value       = data.checkpoint_management_nat_rule.this.auto_generated
}

output "comments" {
  description = "returns a string"
  value       = data.checkpoint_management_nat_rule.this.comments
}

output "enabled" {
  description = "returns a bool"
  value       = data.checkpoint_management_nat_rule.this.enabled
}

output "id" {
  description = "returns a string"
  value       = data.checkpoint_management_nat_rule.this.id
}

output "install_on" {
  description = "returns a set of string"
  value       = data.checkpoint_management_nat_rule.this.install_on
}

output "method" {
  description = "returns a string"
  value       = data.checkpoint_management_nat_rule.this.method
}

output "original_destination" {
  description = "returns a string"
  value       = data.checkpoint_management_nat_rule.this.original_destination
}

output "original_service" {
  description = "returns a string"
  value       = data.checkpoint_management_nat_rule.this.original_service
}

output "original_source" {
  description = "returns a string"
  value       = data.checkpoint_management_nat_rule.this.original_source
}

output "translated_destination" {
  description = "returns a string"
  value       = data.checkpoint_management_nat_rule.this.translated_destination
}

output "translated_service" {
  description = "returns a string"
  value       = data.checkpoint_management_nat_rule.this.translated_service
}

output "translated_source" {
  description = "returns a string"
  value       = data.checkpoint_management_nat_rule.this.translated_source
}

output "this" {
  value = checkpoint_management_nat_rule.this
}
```

[top](#index)