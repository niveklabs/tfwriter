# fortios_system_license_forticare

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
module "fortios_system_license_forticare" {
  source = "./modules/fortios/r/fortios_system_license_forticare"

  # registration_code - (required) is a type of string
  registration_code = null
}
```

[top](#index)

### Variables

```terraform
variable "registration_code" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_license_forticare" "this" {
  # registration_code - (required) is a type of string
  registration_code = var.registration_code
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_system_license_forticare.this.id
}

output "this" {
  value = fortios_system_license_forticare.this
}
```

[top](#index)