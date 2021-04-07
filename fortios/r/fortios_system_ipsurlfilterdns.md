# fortios_system_ipsurlfilterdns

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
module "fortios_system_ipsurlfilterdns" {
  source = "./modules/fortios/r/fortios_system_ipsurlfilterdns"

  # address - (optional) is a type of string
  address = null
  # ipv6_capability - (optional) is a type of string
  ipv6_capability = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv6_capability" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_ipsurlfilterdns" "this" {
  # address - (optional) is a type of string
  address = var.address
  # ipv6_capability - (optional) is a type of string
  ipv6_capability = var.ipv6_capability
  # status - (optional) is a type of string
  status = var.status
}
```

[top](#index)

### Outputs

```terraform
output "address" {
  description = "returns a string"
  value       = fortios_system_ipsurlfilterdns.this.address
}

output "id" {
  description = "returns a string"
  value       = fortios_system_ipsurlfilterdns.this.id
}

output "ipv6_capability" {
  description = "returns a string"
  value       = fortios_system_ipsurlfilterdns.this.ipv6_capability
}

output "status" {
  description = "returns a string"
  value       = fortios_system_ipsurlfilterdns.this.status
}

output "this" {
  value = fortios_system_ipsurlfilterdns.this
}
```

[top](#index)