# triton_firewall_rule

[back](../triton.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    triton = ">= 0.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "triton_firewall_rule" {
  source = "./modules/triton/r/triton_firewall_rule"

  # description - (optional) is a type of string
  description = null
  # enabled - (optional) is a type of bool
  enabled = null
  # rule - (required) is a type of string
  rule = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Human-readable description of the rule"
  type        = string
  default     = null
}

variable "enabled" {
  description = "(optional) - Indicates if the rule is enabled"
  type        = bool
  default     = null
}

variable "rule" {
  description = "(required) - firewall rule text"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "triton_firewall_rule" "this" {
  # description - (optional) is a type of string
  description = var.description
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # rule - (required) is a type of string
  rule = var.rule
}
```

[top](#index)

### Outputs

```terraform
output "global" {
  description = "returns a bool"
  value       = triton_firewall_rule.this.global
}

output "id" {
  description = "returns a string"
  value       = triton_firewall_rule.this.id
}

output "this" {
  value = triton_firewall_rule.this
}
```

[top](#index)