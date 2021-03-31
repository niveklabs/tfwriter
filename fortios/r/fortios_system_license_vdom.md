# fortios_system_license_vdom

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
module "fortios_system_license_vdom" {
  source = "./modules/fortios/r/fortios_system_license_vdom"

  # license - (required) is a type of string
  license = null
}
```

[top](#index)

### Variables

```terraform
variable "license" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_license_vdom" "this" {
  license = var.license
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_system_license_vdom.this.id
}

output "this" {
  value = fortios_system_license_vdom.this
}
```

[top](#index)