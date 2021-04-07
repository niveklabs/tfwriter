# fortios_ips_settings

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
module "fortios_ips_settings" {
  source = "./modules/fortios/r/fortios_ips_settings"

  # ips_packet_quota - (optional) is a type of number
  ips_packet_quota = null
  # packet_log_history - (optional) is a type of number
  packet_log_history = null
  # packet_log_memory - (optional) is a type of number
  packet_log_memory = null
  # packet_log_post_attack - (optional) is a type of number
  packet_log_post_attack = null
}
```

[top](#index)

### Variables

```terraform
variable "ips_packet_quota" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "packet_log_history" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "packet_log_memory" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "packet_log_post_attack" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_ips_settings" "this" {
  # ips_packet_quota - (optional) is a type of number
  ips_packet_quota = var.ips_packet_quota
  # packet_log_history - (optional) is a type of number
  packet_log_history = var.packet_log_history
  # packet_log_memory - (optional) is a type of number
  packet_log_memory = var.packet_log_memory
  # packet_log_post_attack - (optional) is a type of number
  packet_log_post_attack = var.packet_log_post_attack
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_ips_settings.this.id
}

output "ips_packet_quota" {
  description = "returns a number"
  value       = fortios_ips_settings.this.ips_packet_quota
}

output "packet_log_history" {
  description = "returns a number"
  value       = fortios_ips_settings.this.packet_log_history
}

output "packet_log_memory" {
  description = "returns a number"
  value       = fortios_ips_settings.this.packet_log_memory
}

output "packet_log_post_attack" {
  description = "returns a number"
  value       = fortios_ips_settings.this.packet_log_post_attack
}

output "this" {
  value = fortios_ips_settings.this
}
```

[top](#index)