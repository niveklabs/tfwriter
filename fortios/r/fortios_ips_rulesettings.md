# fortios_ips_rulesettings

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
module "fortios_ips_rulesettings" {
  source = "./modules/fortios/r/fortios_ips_rulesettings"

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
resource "fortios_ips_rulesettings" "this" {
  fosid = var.fosid
}
```

[top](#index)

### Outputs

```terraform
output "fosid" {
  description = "returns a number"
  value       = fortios_ips_rulesettings.this.fosid
}

output "id" {
  description = "returns a string"
  value       = fortios_ips_rulesettings.this.id
}

output "this" {
  value = fortios_ips_rulesettings.this
}
```

[top](#index)