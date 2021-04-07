# akamai_appsec_rate_policy

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
module "akamai_appsec_rate_policy" {
  source = "./modules/akamai/r/akamai_appsec_rate_policy"

  # config_id - (required) is a type of number
  config_id = null
  # rate_policy - (required) is a type of string
  rate_policy = null
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

variable "rate_policy" {
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
resource "akamai_appsec_rate_policy" "this" {
  # config_id - (required) is a type of number
  config_id = var.config_id
  # rate_policy - (required) is a type of string
  rate_policy = var.rate_policy
  # version - (required) is a type of number
  version = var.version
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = akamai_appsec_rate_policy.this.id
}

output "rate_policy_id" {
  description = "returns a number"
  value       = akamai_appsec_rate_policy.this.rate_policy_id
}

output "this" {
  value = akamai_appsec_rate_policy.this
}
```

[top](#index)