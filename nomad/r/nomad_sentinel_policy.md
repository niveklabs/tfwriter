# nomad_sentinel_policy

[back](../nomad.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nomad = ">= 1.4.14"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nomad_sentinel_policy" {
  source = "./modules/nomad/r/nomad_sentinel_policy"

  # description - (optional) is a type of string
  description = null
  # enforcement_level - (required) is a type of string
  enforcement_level = null
  # name - (required) is a type of string
  name = null
  # policy - (required) is a type of string
  policy = null
  # scope - (required) is a type of string
  scope = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description for this policy."
  type        = string
  default     = null
}

variable "enforcement_level" {
  description = "(required) - Specifies the enforcement level of the policy."
  type        = string
}

variable "name" {
  description = "(required) - Unique name for this policy."
  type        = string
}

variable "policy" {
  description = "(required) - The Sentinel policy."
  type        = string
}

variable "scope" {
  description = "(required) - Specifies the scope for this policy. Only 'submit-job' is currently supported."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "nomad_sentinel_policy" "this" {
  # description - (optional) is a type of string
  description = var.description
  # enforcement_level - (required) is a type of string
  enforcement_level = var.enforcement_level
  # name - (required) is a type of string
  name = var.name
  # policy - (required) is a type of string
  policy = var.policy
  # scope - (required) is a type of string
  scope = var.scope
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = nomad_sentinel_policy.this.id
}

output "this" {
  value = nomad_sentinel_policy.this
}
```

[top](#index)