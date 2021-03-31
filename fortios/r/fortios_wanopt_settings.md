# fortios_wanopt_settings

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_wanopt_settings" {
  source = "./modules/fortios/r/fortios_wanopt_settings"

  # auto_detect_algorithm - (optional) is a type of string
  auto_detect_algorithm = null
  # host_id - (required) is a type of string
  host_id = null
  # tunnel_ssl_algorithm - (optional) is a type of string
  tunnel_ssl_algorithm = null
}
```

[top](#index)

### Variables

```terraform
variable "auto_detect_algorithm" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "host_id" {
  description = "(required)"
  type        = string
}

variable "tunnel_ssl_algorithm" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_wanopt_settings" "this" {
  auto_detect_algorithm = var.auto_detect_algorithm
  host_id               = var.host_id
  tunnel_ssl_algorithm  = var.tunnel_ssl_algorithm
}
```

[top](#index)

### Outputs

```terraform
output "auto_detect_algorithm" {
  description = "returns a string"
  value       = fortios_wanopt_settings.this.auto_detect_algorithm
}

output "id" {
  description = "returns a string"
  value       = fortios_wanopt_settings.this.id
}

output "tunnel_ssl_algorithm" {
  description = "returns a string"
  value       = fortios_wanopt_settings.this.tunnel_ssl_algorithm
}

output "this" {
  value = fortios_wanopt_settings.this
}
```

[top](#index)