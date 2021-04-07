# akamai_appsec_waf_protection

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
module "akamai_appsec_waf_protection" {
  source = "./modules/akamai/r/akamai_appsec_waf_protection"

  # config_id - (required) is a type of number
  config_id = null
  # enabled - (required) is a type of bool
  enabled = null
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

variable "enabled" {
  description = "(required)"
  type        = bool
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
resource "akamai_appsec_waf_protection" "this" {
  # config_id - (required) is a type of number
  config_id = var.config_id
  # enabled - (required) is a type of bool
  enabled = var.enabled
  # security_policy_id - (required) is a type of string
  security_policy_id = var.security_policy_id
  # version - (required) is a type of number
  version = var.version
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = akamai_appsec_waf_protection.this.id
}

output "output_text" {
  description = "returns a string"
  value       = akamai_appsec_waf_protection.this.output_text
}

output "this" {
  value = akamai_appsec_waf_protection.this
}
```

[top](#index)