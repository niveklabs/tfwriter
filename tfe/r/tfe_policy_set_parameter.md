# tfe_policy_set_parameter

[back](../tfe.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tfe = ">= 0.24.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tfe_policy_set_parameter" {
  source = "./modules/tfe/r/tfe_policy_set_parameter"

  # key - (required) is a type of string
  key = null
  # policy_set_id - (required) is a type of string
  policy_set_id = null
  # sensitive - (optional) is a type of bool
  sensitive = null
  # value - (optional) is a type of string
  value = null
}
```

[top](#index)

### Variables

```terraform
variable "key" {
  description = "(required)"
  type        = string
}

variable "policy_set_id" {
  description = "(required)"
  type        = string
}

variable "sensitive" {
  description = "(optional)"
  type        = bool
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
resource "tfe_policy_set_parameter" "this" {
  key           = var.key
  policy_set_id = var.policy_set_id
  sensitive     = var.sensitive
  value         = var.value
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tfe_policy_set_parameter.this.id
}

output "this" {
  value = tfe_policy_set_parameter.this
}
```

[top](#index)