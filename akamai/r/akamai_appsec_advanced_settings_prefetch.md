# akamai_appsec_advanced_settings_prefetch

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
module "akamai_appsec_advanced_settings_prefetch" {
  source = "./modules/akamai/r/akamai_appsec_advanced_settings_prefetch"

  # all_extensions - (required) is a type of bool
  all_extensions = null
  # config_id - (required) is a type of number
  config_id = null
  # enable_app_layer - (required) is a type of bool
  enable_app_layer = null
  # enable_rate_controls - (required) is a type of bool
  enable_rate_controls = null
  # extensions - (required) is a type of list of string
  extensions = []
  # version - (required) is a type of number
  version = null
}
```

[top](#index)

### Variables

```terraform
variable "all_extensions" {
  description = "(required)"
  type        = bool
}

variable "config_id" {
  description = "(required)"
  type        = number
}

variable "enable_app_layer" {
  description = "(required)"
  type        = bool
}

variable "enable_rate_controls" {
  description = "(required)"
  type        = bool
}

variable "extensions" {
  description = "(required) - List of extensions"
  type        = list(string)
}

variable "version" {
  description = "(required)"
  type        = number
}
```

[top](#index)

### Resource

```terraform
resource "akamai_appsec_advanced_settings_prefetch" "this" {
  all_extensions       = var.all_extensions
  config_id            = var.config_id
  enable_app_layer     = var.enable_app_layer
  enable_rate_controls = var.enable_rate_controls
  extensions           = var.extensions
  version              = var.version
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = akamai_appsec_advanced_settings_prefetch.this.id
}

output "this" {
  value = akamai_appsec_advanced_settings_prefetch.this
}
```

[top](#index)