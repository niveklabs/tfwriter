# fortios_lognulldevice_setting

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
module "fortios_lognulldevice_setting" {
  source = "./modules/fortios/r/fortios_lognulldevice_setting"

  # status - (required) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "status" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "fortios_lognulldevice_setting" "this" {
  status = var.status
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_lognulldevice_setting.this.id
}

output "this" {
  value = fortios_lognulldevice_setting.this
}
```

[top](#index)