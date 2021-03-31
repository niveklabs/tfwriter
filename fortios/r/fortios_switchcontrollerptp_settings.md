# fortios_switchcontrollerptp_settings

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
module "fortios_switchcontrollerptp_settings" {
  source = "./modules/fortios/r/fortios_switchcontrollerptp_settings"

  # mode - (optional) is a type of string
  mode = null
}
```

[top](#index)

### Variables

```terraform
variable "mode" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_switchcontrollerptp_settings" "this" {
  mode = var.mode
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_switchcontrollerptp_settings.this.id
}

output "mode" {
  description = "returns a string"
  value       = fortios_switchcontrollerptp_settings.this.mode
}

output "this" {
  value = fortios_switchcontrollerptp_settings.this
}
```

[top](#index)