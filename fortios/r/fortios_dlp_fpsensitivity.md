# fortios_dlp_fpsensitivity

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
module "fortios_dlp_fpsensitivity" {
  source = "./modules/fortios/r/fortios_dlp_fpsensitivity"

  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_dlp_fpsensitivity" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_dlp_fpsensitivity.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_dlp_fpsensitivity.this.name
}

output "this" {
  value = fortios_dlp_fpsensitivity.this
}
```

[top](#index)