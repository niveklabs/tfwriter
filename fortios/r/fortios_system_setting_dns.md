# fortios_system_setting_dns

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
module "fortios_system_setting_dns" {
  source = "./modules/fortios/r/fortios_system_setting_dns"

  # dns_over_tls - (optional) is a type of string
  dns_over_tls = null
  # primary - (optional) is a type of string
  primary = null
  # secondary - (optional) is a type of string
  secondary = null
}
```

[top](#index)

### Variables

```terraform
variable "dns_over_tls" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "primary" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "secondary" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_setting_dns" "this" {
  dns_over_tls = var.dns_over_tls
  primary      = var.primary
  secondary    = var.secondary
}
```

[top](#index)

### Outputs

```terraform
output "dns_over_tls" {
  description = "returns a string"
  value       = fortios_system_setting_dns.this.dns_over_tls
}

output "id" {
  description = "returns a string"
  value       = fortios_system_setting_dns.this.id
}

output "primary" {
  description = "returns a string"
  value       = fortios_system_setting_dns.this.primary
}

output "secondary" {
  description = "returns a string"
  value       = fortios_system_setting_dns.this.secondary
}

output "this" {
  value = fortios_system_setting_dns.this
}
```

[top](#index)