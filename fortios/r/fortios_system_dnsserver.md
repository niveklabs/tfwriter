# fortios_system_dnsserver

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
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_system_dnsserver" {
  source = "./modules/fortios/r/fortios_system_dnsserver"

  # dnsfilter_profile - (optional) is a type of string
  dnsfilter_profile = null
  # mode - (optional) is a type of string
  mode = null
  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "dnsfilter_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_dnsserver" "this" {
  dnsfilter_profile = var.dnsfilter_profile
  mode              = var.mode
  name              = var.name
}
```

[top](#index)

### Outputs

```terraform
output "dnsfilter_profile" {
  description = "returns a string"
  value       = fortios_system_dnsserver.this.dnsfilter_profile
}

output "id" {
  description = "returns a string"
  value       = fortios_system_dnsserver.this.id
}

output "mode" {
  description = "returns a string"
  value       = fortios_system_dnsserver.this.mode
}

output "name" {
  description = "returns a string"
  value       = fortios_system_dnsserver.this.name
}

output "this" {
  value = fortios_system_dnsserver.this
}
```

[top](#index)