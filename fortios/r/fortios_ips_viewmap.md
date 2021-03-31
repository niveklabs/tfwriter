# fortios_ips_viewmap

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
module "fortios_ips_viewmap" {
  source = "./modules/fortios/r/fortios_ips_viewmap"

  # fosid - (optional) is a type of number
  fosid = null
  # id_policy_id - (optional) is a type of number
  id_policy_id = null
  # policy_id - (optional) is a type of number
  policy_id = null
  # vdom_id - (optional) is a type of number
  vdom_id = null
  # which - (optional) is a type of string
  which = null
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

variable "id_policy_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "policy_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "vdom_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "which" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_ips_viewmap" "this" {
  fosid        = var.fosid
  id_policy_id = var.id_policy_id
  policy_id    = var.policy_id
  vdom_id      = var.vdom_id
  which        = var.which
}
```

[top](#index)

### Outputs

```terraform
output "fosid" {
  description = "returns a number"
  value       = fortios_ips_viewmap.this.fosid
}

output "id" {
  description = "returns a string"
  value       = fortios_ips_viewmap.this.id
}

output "id_policy_id" {
  description = "returns a number"
  value       = fortios_ips_viewmap.this.id_policy_id
}

output "policy_id" {
  description = "returns a number"
  value       = fortios_ips_viewmap.this.policy_id
}

output "vdom_id" {
  description = "returns a number"
  value       = fortios_ips_viewmap.this.vdom_id
}

output "which" {
  description = "returns a string"
  value       = fortios_ips_viewmap.this.which
}

output "this" {
  value = fortios_ips_viewmap.this
}
```

[top](#index)