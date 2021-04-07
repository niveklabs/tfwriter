# fortios_application_rulesettings

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
module "fortios_application_rulesettings" {
  source = "./modules/fortios/r/fortios_application_rulesettings"

  # fosid - (optional) is a type of number
  fosid = null
}
```

[top](#index)

### Variables

```terraform
variable "fosid" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_application_rulesettings" "this" {
  # fosid - (optional) is a type of number
  fosid = var.fosid
}
```

[top](#index)

### Outputs

```terraform
output "fosid" {
  description = "returns a number"
  value       = fortios_application_rulesettings.this.fosid
}

output "id" {
  description = "returns a string"
  value       = fortios_application_rulesettings.this.id
}

output "this" {
  value = fortios_application_rulesettings.this
}
```

[top](#index)