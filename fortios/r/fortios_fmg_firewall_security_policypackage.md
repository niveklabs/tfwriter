# fortios_fmg_firewall_security_policypackage

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
module "fortios_fmg_firewall_security_policypackage" {
  source = "./modules/fortios/r/fortios_fmg_firewall_security_policypackage"

  # adom - (optional) is a type of string
  adom = null
  # inspection_mode - (optional) is a type of string
  inspection_mode = null
  # name - (required) is a type of string
  name = null
  # target - (optional) is a type of string
  target = null
  # vdom - (optional) is a type of string
  vdom = null
}
```

[top](#index)

### Variables

```terraform
variable "adom" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "inspection_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "target" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vdom" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_fmg_firewall_security_policypackage" "this" {
  adom            = var.adom
  inspection_mode = var.inspection_mode
  name            = var.name
  target          = var.target
  vdom            = var.vdom
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_fmg_firewall_security_policypackage.this.id
}

output "this" {
  value = fortios_fmg_firewall_security_policypackage.this
}
```

[top](#index)