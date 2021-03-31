# fortios_switchcontrollerqos_qospolicy

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
module "fortios_switchcontrollerqos_qospolicy" {
  source = "./modules/fortios/r/fortios_switchcontrollerqos_qospolicy"

  # default_cos - (required) is a type of number
  default_cos = null
  # name - (required) is a type of string
  name = null
  # queue_policy - (optional) is a type of string
  queue_policy = null
  # trust_dot1p_map - (optional) is a type of string
  trust_dot1p_map = null
  # trust_ip_dscp_map - (optional) is a type of string
  trust_ip_dscp_map = null
}
```

[top](#index)

### Variables

```terraform
variable "default_cos" {
  description = "(required)"
  type        = number
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "queue_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "trust_dot1p_map" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "trust_ip_dscp_map" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_switchcontrollerqos_qospolicy" "this" {
  default_cos       = var.default_cos
  name              = var.name
  queue_policy      = var.queue_policy
  trust_dot1p_map   = var.trust_dot1p_map
  trust_ip_dscp_map = var.trust_ip_dscp_map
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_switchcontrollerqos_qospolicy.this.id
}

output "queue_policy" {
  description = "returns a string"
  value       = fortios_switchcontrollerqos_qospolicy.this.queue_policy
}

output "trust_dot1p_map" {
  description = "returns a string"
  value       = fortios_switchcontrollerqos_qospolicy.this.trust_dot1p_map
}

output "trust_ip_dscp_map" {
  description = "returns a string"
  value       = fortios_switchcontrollerqos_qospolicy.this.trust_ip_dscp_map
}

output "this" {
  value = fortios_switchcontrollerqos_qospolicy.this
}
```

[top](#index)