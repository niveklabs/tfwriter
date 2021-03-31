# akamai_appsec_siem_settings

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
module "akamai_appsec_siem_settings" {
  source = "./modules/akamai/r/akamai_appsec_siem_settings"

  # config_id - (required) is a type of number
  config_id = null
  # enable_botman_siem - (optional) is a type of bool
  enable_botman_siem = null
  # enable_for_all_policies - (required) is a type of bool
  enable_for_all_policies = null
  # enable_siem - (required) is a type of bool
  enable_siem = null
  # security_policy_ids - (required) is a type of list of string
  security_policy_ids = []
  # siem_id - (required) is a type of number
  siem_id = null
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

variable "enable_botman_siem" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_for_all_policies" {
  description = "(required)"
  type        = bool
}

variable "enable_siem" {
  description = "(required)"
  type        = bool
}

variable "security_policy_ids" {
  description = "(required)"
  type        = list(string)
}

variable "siem_id" {
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
resource "akamai_appsec_siem_settings" "this" {
  config_id               = var.config_id
  enable_botman_siem      = var.enable_botman_siem
  enable_for_all_policies = var.enable_for_all_policies
  enable_siem             = var.enable_siem
  security_policy_ids     = var.security_policy_ids
  siem_id                 = var.siem_id
  version                 = var.version
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = akamai_appsec_siem_settings.this.id
}

output "output_text" {
  description = "returns a string"
  value       = akamai_appsec_siem_settings.this.output_text
}

output "this" {
  value = akamai_appsec_siem_settings.this
}
```

[top](#index)