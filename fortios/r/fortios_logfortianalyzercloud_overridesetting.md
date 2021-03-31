# fortios_logfortianalyzercloud_overridesetting

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
module "fortios_logfortianalyzercloud_overridesetting" {
  source = "./modules/fortios/r/fortios_logfortianalyzercloud_overridesetting"

  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_logfortianalyzercloud_overridesetting" "this" {
  status = var.status
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_logfortianalyzercloud_overridesetting.this.id
}

output "status" {
  description = "returns a string"
  value       = fortios_logfortianalyzercloud_overridesetting.this.status
}

output "this" {
  value = fortios_logfortianalyzercloud_overridesetting.this
}
```

[top](#index)