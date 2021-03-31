# fortios_switchcontrollersecuritypolicy_captiveportal

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
module "fortios_switchcontrollersecuritypolicy_captiveportal" {
  source = "./modules/fortios/r/fortios_switchcontrollersecuritypolicy_captiveportal"

  # name - (optional) is a type of string
  name = null
  # policy_type - (optional) is a type of string
  policy_type = null
  # vlan - (optional) is a type of string
  vlan = null
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

variable "policy_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vlan" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_switchcontrollersecuritypolicy_captiveportal" "this" {
  name        = var.name
  policy_type = var.policy_type
  vlan        = var.vlan
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_switchcontrollersecuritypolicy_captiveportal.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_switchcontrollersecuritypolicy_captiveportal.this.name
}

output "policy_type" {
  description = "returns a string"
  value       = fortios_switchcontrollersecuritypolicy_captiveportal.this.policy_type
}

output "vlan" {
  description = "returns a string"
  value       = fortios_switchcontrollersecuritypolicy_captiveportal.this.vlan
}

output "this" {
  value = fortios_switchcontrollersecuritypolicy_captiveportal.this
}
```

[top](#index)