# fortios_fmg_system_dns

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
module "fortios_fmg_system_dns" {
  source = "./modules/fortios/r/fortios_fmg_system_dns"

  # primary - (optional) is a type of string
  primary = null
  # secondary - (optional) is a type of string
  secondary = null
}
```

[top](#index)

### Variables

```terraform
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
resource "fortios_fmg_system_dns" "this" {
  primary   = var.primary
  secondary = var.secondary
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_fmg_system_dns.this.id
}

output "this" {
  value = fortios_fmg_system_dns.this
}
```

[top](#index)