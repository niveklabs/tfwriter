# akamai_appsec_slow_post

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
module "akamai_appsec_slow_post" {
  source = "./modules/akamai/r/akamai_appsec_slow_post"

  # config_id - (required) is a type of number
  config_id = null
  # duration_threshold_timeout - (optional) is a type of number
  duration_threshold_timeout = null
  # security_policy_id - (required) is a type of string
  security_policy_id = null
  # slow_rate_action - (required) is a type of string
  slow_rate_action = null
  # slow_rate_threshold_period - (required) is a type of number
  slow_rate_threshold_period = null
  # slow_rate_threshold_rate - (required) is a type of number
  slow_rate_threshold_rate = null
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

variable "duration_threshold_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "security_policy_id" {
  description = "(required)"
  type        = string
}

variable "slow_rate_action" {
  description = "(required)"
  type        = string
}

variable "slow_rate_threshold_period" {
  description = "(required)"
  type        = number
}

variable "slow_rate_threshold_rate" {
  description = "(required)"
  type        = number
}

variable "version" {
  description = "(required)"
  type        = number
}
```

[top](#index)

### Resource

```terraform
resource "akamai_appsec_slow_post" "this" {
  # config_id - (required) is a type of number
  config_id = var.config_id
  # duration_threshold_timeout - (optional) is a type of number
  duration_threshold_timeout = var.duration_threshold_timeout
  # security_policy_id - (required) is a type of string
  security_policy_id = var.security_policy_id
  # slow_rate_action - (required) is a type of string
  slow_rate_action = var.slow_rate_action
  # slow_rate_threshold_period - (required) is a type of number
  slow_rate_threshold_period = var.slow_rate_threshold_period
  # slow_rate_threshold_rate - (required) is a type of number
  slow_rate_threshold_rate = var.slow_rate_threshold_rate
  # version - (required) is a type of number
  version = var.version
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = akamai_appsec_slow_post.this.id
}

output "this" {
  value = akamai_appsec_slow_post.this
}
```

[top](#index)