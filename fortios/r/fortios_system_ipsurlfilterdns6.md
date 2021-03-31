# fortios_system_ipsurlfilterdns6

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
module "fortios_system_ipsurlfilterdns6" {
  source = "./modules/fortios/r/fortios_system_ipsurlfilterdns6"

  # address6 - (optional) is a type of string
  address6 = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "address6" {
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
resource "fortios_system_ipsurlfilterdns6" "this" {
  address6 = var.address6
  status   = var.status
}
```

[top](#index)

### Outputs

```terraform
output "address6" {
  description = "returns a string"
  value       = fortios_system_ipsurlfilterdns6.this.address6
}

output "id" {
  description = "returns a string"
  value       = fortios_system_ipsurlfilterdns6.this.id
}

output "status" {
  description = "returns a string"
  value       = fortios_system_ipsurlfilterdns6.this.status
}

output "this" {
  value = fortios_system_ipsurlfilterdns6.this
}
```

[top](#index)