# fortios_firewall_dnstranslation

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
module "fortios_firewall_dnstranslation" {
  source = "./modules/fortios/r/fortios_firewall_dnstranslation"

  # dst - (optional) is a type of string
  dst = null
  # fosid - (optional) is a type of number
  fosid = null
  # netmask - (optional) is a type of string
  netmask = null
  # src - (optional) is a type of string
  src = null
}
```

[top](#index)

### Variables

```terraform
variable "dst" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fosid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "netmask" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "src" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewall_dnstranslation" "this" {
  # dst - (optional) is a type of string
  dst = var.dst
  # fosid - (optional) is a type of number
  fosid = var.fosid
  # netmask - (optional) is a type of string
  netmask = var.netmask
  # src - (optional) is a type of string
  src = var.src
}
```

[top](#index)

### Outputs

```terraform
output "dst" {
  description = "returns a string"
  value       = fortios_firewall_dnstranslation.this.dst
}

output "fosid" {
  description = "returns a number"
  value       = fortios_firewall_dnstranslation.this.fosid
}

output "id" {
  description = "returns a string"
  value       = fortios_firewall_dnstranslation.this.id
}

output "netmask" {
  description = "returns a string"
  value       = fortios_firewall_dnstranslation.this.netmask
}

output "src" {
  description = "returns a string"
  value       = fortios_firewall_dnstranslation.this.src
}

output "this" {
  value = fortios_firewall_dnstranslation.this
}
```

[top](#index)