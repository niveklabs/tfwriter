# fortios_fmg_system_license_forticare

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
module "fortios_fmg_system_license_forticare" {
  source = "./modules/fortios/r/fortios_fmg_system_license_forticare"

  # adom - (optional) is a type of string
  adom = null
  # registration_code - (required) is a type of string
  registration_code = null
  # target - (required) is a type of string
  target = null
}
```

[top](#index)

### Variables

```terraform
variable "adom" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "registration_code" {
  description = "(required)"
  type        = string
}

variable "target" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "fortios_fmg_system_license_forticare" "this" {
  adom              = var.adom
  registration_code = var.registration_code
  target            = var.target
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_fmg_system_license_forticare.this.id
}

output "this" {
  value = fortios_fmg_system_license_forticare.this
}
```

[top](#index)