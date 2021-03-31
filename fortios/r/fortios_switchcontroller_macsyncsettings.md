# fortios_switchcontroller_macsyncsettings

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
module "fortios_switchcontroller_macsyncsettings" {
  source = "./modules/fortios/r/fortios_switchcontroller_macsyncsettings"

  # mac_sync_interval - (optional) is a type of number
  mac_sync_interval = null
}
```

[top](#index)

### Variables

```terraform
variable "mac_sync_interval" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_switchcontroller_macsyncsettings" "this" {
  mac_sync_interval = var.mac_sync_interval
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_switchcontroller_macsyncsettings.this.id
}

output "mac_sync_interval" {
  description = "returns a number"
  value       = fortios_switchcontroller_macsyncsettings.this.mac_sync_interval
}

output "this" {
  value = fortios_switchcontroller_macsyncsettings.this
}
```

[top](#index)