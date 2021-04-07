# akamai_appsec_custom_deny

[back](../akamai.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/akamai/d/akamai_appsec_custom_deny"

  # config_id - (required) is a type of number
  config_id = null
  # custom_deny_id - (optional) is a type of string
  custom_deny_id = null
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

variable "custom_deny_id" {
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

### Datasource

```terraform
data "akamai_appsec_custom_deny" "this" {
  # config_id - (required) is a type of number
  config_id = var.config_id
  # custom_deny_id - (optional) is a type of string
  custom_deny_id = var.custom_deny_id
  # version - (required) is a type of number
  version = var.version
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.akamai_appsec_custom_deny.this.id
}

output "json" {
  description = "returns a string"
  value       = data.akamai_appsec_custom_deny.this.json
}

output "output_text" {
  description = "returns a string"
  value       = data.akamai_appsec_custom_deny.this.output_text
}

output "this" {
  value = akamai_appsec_custom_deny.this
}
```

[top](#index)