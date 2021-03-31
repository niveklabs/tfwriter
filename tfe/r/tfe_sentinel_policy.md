# tfe_sentinel_policy

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
module "tfe_sentinel_policy" {
  source = "./modules/tfe/r/tfe_sentinel_policy"

  # description - (optional) is a type of string
  description = null
  # enforce_mode - (optional) is a type of string
  enforce_mode = null
  # name - (required) is a type of string
  name = null
  # organization - (required) is a type of string
  organization = null
  # policy - (required) is a type of string
  policy = null
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

variable "enforce_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "organization" {
  description = "(required)"
  type        = string
}

variable "policy" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tfe_sentinel_policy" "this" {
  description  = var.description
  enforce_mode = var.enforce_mode
  name         = var.name
  organization = var.organization
  policy       = var.policy
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = tfe_sentinel_policy.this.description
}

output "id" {
  description = "returns a string"
  value       = tfe_sentinel_policy.this.id
}

output "this" {
  value = tfe_sentinel_policy.this
}
```

[top](#index)