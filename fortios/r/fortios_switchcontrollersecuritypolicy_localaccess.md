# fortios_switchcontrollersecuritypolicy_localaccess

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
module "fortios_switchcontrollersecuritypolicy_localaccess" {
  source = "./modules/fortios/r/fortios_switchcontrollersecuritypolicy_localaccess"

  # internal_allowaccess - (optional) is a type of string
  internal_allowaccess = null
  # mgmt_allowaccess - (optional) is a type of string
  mgmt_allowaccess = null
  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "internal_allowaccess" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mgmt_allowaccess" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_switchcontrollersecuritypolicy_localaccess" "this" {
  internal_allowaccess = var.internal_allowaccess
  mgmt_allowaccess     = var.mgmt_allowaccess
  name                 = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_switchcontrollersecuritypolicy_localaccess.this.id
}

output "internal_allowaccess" {
  description = "returns a string"
  value       = fortios_switchcontrollersecuritypolicy_localaccess.this.internal_allowaccess
}

output "mgmt_allowaccess" {
  description = "returns a string"
  value       = fortios_switchcontrollersecuritypolicy_localaccess.this.mgmt_allowaccess
}

output "name" {
  description = "returns a string"
  value       = fortios_switchcontrollersecuritypolicy_localaccess.this.name
}

output "this" {
  value = fortios_switchcontrollersecuritypolicy_localaccess.this
}
```

[top](#index)