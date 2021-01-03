# fortios_fmg_system_ntp

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
module "fortios_fmg_system_ntp" {
  source = "./modules/fortios/r/fortios_fmg_system_ntp"

  # server - (required) is a type of string
  server = null
  # status - (optional) is a type of string
  status = null
  # sync_interval - (optional) is a type of number
  sync_interval = null
}
```

[top](#index)

### Variables

```terraform
variable "server" {
  description = "(required)"
  type        = string
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sync_interval" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_fmg_system_ntp" "this" {
  server        = var.server
  status        = var.status
  sync_interval = var.sync_interval
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_fmg_system_ntp.this.id
}

output "this" {
  value = fortios_fmg_system_ntp.this
}
```

[top](#index)