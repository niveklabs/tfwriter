# akamai_appsec_advanced_settings_logging

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
module "akamai_appsec_advanced_settings_logging" {
  source = "./modules/akamai/r/akamai_appsec_advanced_settings_logging"

  # config_id - (required) is a type of number
  config_id = null
  # logging - (required) is a type of string
  logging = null
  # security_policy_id - (optional) is a type of string
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

variable "logging" {
  description = "(required)"
  type        = string
}

variable "security_policy_id" {
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
resource "akamai_appsec_advanced_settings_logging" "this" {
  config_id          = var.config_id
  logging            = var.logging
  security_policy_id = var.security_policy_id
  version            = var.version
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = akamai_appsec_advanced_settings_logging.this.id
}

output "this" {
  value = akamai_appsec_advanced_settings_logging.this
}
```

[top](#index)