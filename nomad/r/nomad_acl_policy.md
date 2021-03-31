# nomad_acl_policy

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
    nomad = ">= 1.4.13"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nomad_acl_policy" {
  source = "./modules/nomad/r/nomad_acl_policy"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # rules_hcl - (required) is a type of string
  rules_hcl = null
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

variable "name" {
  description = "(required) - Unique name for this policy."
  type        = string
}

variable "rules_hcl" {
  description = "(required) - HCL or JSON representation of the rules to enforce on this policy. Use file() to specify a file as input."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "nomad_acl_policy" "this" {
  description = var.description
  name        = var.name
  rules_hcl   = var.rules_hcl
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = nomad_acl_policy.this.id
}

output "this" {
  value = nomad_acl_policy.this
}
```

[top](#index)