# akamai_appsec_custom_deny

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
module "akamai_appsec_custom_deny" {
  source = "./modules/akamai/r/akamai_appsec_custom_deny"

  # config_id - (required) is a type of number
  config_id = null
  # custom_deny - (required) is a type of string
  custom_deny = null
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

variable "custom_deny" {
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
resource "akamai_appsec_custom_deny" "this" {
  # config_id - (required) is a type of number
  config_id = var.config_id
  # custom_deny - (required) is a type of string
  custom_deny = var.custom_deny
  # version - (required) is a type of number
  version = var.version
}
```

[top](#index)

### Outputs

```terraform
output "custom_deny_id" {
  description = "returns a string"
  value       = akamai_appsec_custom_deny.this.custom_deny_id
}

output "id" {
  description = "returns a string"
  value       = akamai_appsec_custom_deny.this.id
}

output "this" {
  value = akamai_appsec_custom_deny.this
}
```

[top](#index)