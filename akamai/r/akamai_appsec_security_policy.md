# akamai_appsec_security_policy

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
    akamai = ">= 1.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "akamai_appsec_security_policy" {
  source = "./modules/akamai/r/akamai_appsec_security_policy"

  # config_id - (required) is a type of number
  config_id = null
  # default_settings - (optional) is a type of bool
  default_settings = null
  # security_policy_name - (required) is a type of string
  security_policy_name = null
  # security_policy_prefix - (required) is a type of string
  security_policy_prefix = null
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

variable "default_settings" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "security_policy_name" {
  description = "(required)"
  type        = string
}

variable "security_policy_prefix" {
  description = "(required)"
  type        = string
}

variable "version" {
  description = "(required)"
  type        = number
}
```

[top](#index)

### Resource

```terraform
resource "akamai_appsec_security_policy" "this" {
  # config_id - (required) is a type of number
  config_id = var.config_id
  # default_settings - (optional) is a type of bool
  default_settings = var.default_settings
  # security_policy_name - (required) is a type of string
  security_policy_name = var.security_policy_name
  # security_policy_prefix - (required) is a type of string
  security_policy_prefix = var.security_policy_prefix
  # version - (required) is a type of number
  version = var.version
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = akamai_appsec_security_policy.this.id
}

output "security_policy_id" {
  description = "returns a string"
  value       = akamai_appsec_security_policy.this.security_policy_id
}

output "this" {
  value = akamai_appsec_security_policy.this
}
```

[top](#index)