# fortios_fmg_system_admin

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
module "fortios_fmg_system_admin" {
  source = "./modules/fortios/r/fortios_fmg_system_admin"

  # http_port - (optional) is a type of number
  http_port = null
  # https_port - (optional) is a type of number
  https_port = null
  # idle_timeout - (optional) is a type of number
  idle_timeout = null
}
```

[top](#index)

### Variables

```terraform
variable "http_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "https_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "idle_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_fmg_system_admin" "this" {
  http_port    = var.http_port
  https_port   = var.https_port
  idle_timeout = var.idle_timeout
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_fmg_system_admin.this.id
}

output "this" {
  value = fortios_fmg_system_admin.this
}
```

[top](#index)