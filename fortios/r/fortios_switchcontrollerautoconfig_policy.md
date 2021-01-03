# fortios_switchcontrollerautoconfig_policy

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
module "fortios_switchcontrollerautoconfig_policy" {
  source = "./modules/fortios/r/fortios_switchcontrollerautoconfig_policy"

  # name - (required) is a type of string
  name = null
  # poe_status - (optional) is a type of string
  poe_status = null
  # qos_policy - (optional) is a type of string
  qos_policy = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "poe_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "qos_policy" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_switchcontrollerautoconfig_policy" "this" {
  name       = var.name
  poe_status = var.poe_status
  qos_policy = var.qos_policy
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_switchcontrollerautoconfig_policy.this.id
}

output "poe_status" {
  description = "returns a string"
  value       = fortios_switchcontrollerautoconfig_policy.this.poe_status
}

output "qos_policy" {
  description = "returns a string"
  value       = fortios_switchcontrollerautoconfig_policy.this.qos_policy
}

output "this" {
  value = fortios_switchcontrollerautoconfig_policy.this
}
```

[top](#index)