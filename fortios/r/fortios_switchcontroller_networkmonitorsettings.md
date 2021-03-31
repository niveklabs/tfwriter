# fortios_switchcontroller_networkmonitorsettings

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
module "fortios_switchcontroller_networkmonitorsettings" {
  source = "./modules/fortios/r/fortios_switchcontroller_networkmonitorsettings"

  # network_monitoring - (optional) is a type of string
  network_monitoring = null
}
```

[top](#index)

### Variables

```terraform
variable "network_monitoring" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_switchcontroller_networkmonitorsettings" "this" {
  network_monitoring = var.network_monitoring
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_switchcontroller_networkmonitorsettings.this.id
}

output "network_monitoring" {
  description = "returns a string"
  value       = fortios_switchcontroller_networkmonitorsettings.this.network_monitoring
}

output "this" {
  value = fortios_switchcontroller_networkmonitorsettings.this
}
```

[top](#index)