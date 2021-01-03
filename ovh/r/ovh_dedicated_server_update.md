# ovh_dedicated_server_update

[back](../ovh.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ovh = ">= 0.10.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ovh_dedicated_server_update" {
  source = "./modules/ovh/r/ovh_dedicated_server_update"

  # boot_id - (optional) is a type of number
  boot_id = null
  # monitoring - (optional) is a type of bool
  monitoring = null
  # service_name - (required) is a type of string
  service_name = null
  # state - (optional) is a type of string
  state = null
}
```

[top](#index)

### Variables

```terraform
variable "boot_id" {
  description = "(optional) - The boot id of your dedicated server."
  type        = number
  default     = null
}

variable "monitoring" {
  description = "(optional) - Icmp monitoring state"
  type        = bool
  default     = null
}

variable "service_name" {
  description = "(required) - The internal name of your dedicated server."
  type        = string
}

variable "state" {
  description = "(optional) - error, hacked, hackedBlocked, ok"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "ovh_dedicated_server_update" "this" {
  boot_id      = var.boot_id
  monitoring   = var.monitoring
  service_name = var.service_name
  state        = var.state
}
```

[top](#index)

### Outputs

```terraform
output "boot_id" {
  description = "returns a number"
  value       = ovh_dedicated_server_update.this.boot_id
}

output "id" {
  description = "returns a string"
  value       = ovh_dedicated_server_update.this.id
}

output "monitoring" {
  description = "returns a bool"
  value       = ovh_dedicated_server_update.this.monitoring
}

output "state" {
  description = "returns a string"
  value       = ovh_dedicated_server_update.this.state
}

output "this" {
  value = ovh_dedicated_server_update.this
}
```

[top](#index)