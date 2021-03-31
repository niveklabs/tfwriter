# akamai_appsec_rate_policy_action

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
module "akamai_appsec_rate_policy_action" {
  source = "./modules/akamai/r/akamai_appsec_rate_policy_action"

  # config_id - (required) is a type of number
  config_id = null
  # ipv4_action - (required) is a type of string
  ipv4_action = null
  # ipv6_action - (required) is a type of string
  ipv6_action = null
  # rate_policy_id - (required) is a type of number
  rate_policy_id = null
  # security_policy_id - (required) is a type of string
  security_policy_id = null
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

variable "ipv4_action" {
  description = "(required)"
  type        = string
}

variable "ipv6_action" {
  description = "(required)"
  type        = string
}

variable "rate_policy_id" {
  description = "(required)"
  type        = number
}

variable "security_policy_id" {
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
resource "akamai_appsec_rate_policy_action" "this" {
  config_id          = var.config_id
  ipv4_action        = var.ipv4_action
  ipv6_action        = var.ipv6_action
  rate_policy_id     = var.rate_policy_id
  security_policy_id = var.security_policy_id
  version            = var.version
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = akamai_appsec_rate_policy_action.this.id
}

output "this" {
  value = akamai_appsec_rate_policy_action.this
}
```

[top](#index)