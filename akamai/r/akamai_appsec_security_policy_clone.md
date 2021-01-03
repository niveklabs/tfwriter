# akamai_appsec_security_policy_clone

[back](../akamai.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    akamai = ">= 1.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "akamai_appsec_security_policy_clone" {
  source = "./modules/akamai/r/akamai_appsec_security_policy_clone"

  # config_id - (required) is a type of number
  config_id = null
  # create_from_security_policy - (required) is a type of string
  create_from_security_policy = null
  # policy_name - (optional) is a type of string
  policy_name = null
  # policy_prefix - (optional) is a type of string
  policy_prefix = null
  # version - (required) is a type of number
  version = null
}
```

[top](#index)

### Variables

```terraform
variable "config_id" {
  description = "(required)"
  type        = number
}

variable "create_from_security_policy" {
  description = "(required)"
  type        = string
}

variable "policy_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "policy_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "version" {
  description = "(required)"
  type        = number
}
```

[top](#index)

### Resource

```terraform
resource "akamai_appsec_security_policy_clone" "this" {
  config_id                   = var.config_id
  create_from_security_policy = var.create_from_security_policy
  policy_name                 = var.policy_name
  policy_prefix               = var.policy_prefix
  version                     = var.version
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = akamai_appsec_security_policy_clone.this.id
}

output "policy_id" {
  description = "returns a string"
  value       = akamai_appsec_security_policy_clone.this.policy_id
}

output "this" {
  value = akamai_appsec_security_policy_clone.this
}
```

[top](#index)