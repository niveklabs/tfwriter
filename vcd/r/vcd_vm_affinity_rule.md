# vcd_vm_affinity_rule

[back](../vcd.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vcd = ">= 3.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vcd_vm_affinity_rule" {
  source = "./modules/vcd/r/vcd_vm_affinity_rule"

  # enabled - (optional) is a type of bool
  enabled = null
  # name - (required) is a type of string
  name = null
  # org - (optional) is a type of string
  org = null
  # polarity - (required) is a type of string
  polarity = null
  # required - (optional) is a type of bool
  required = null
  # vdc - (optional) is a type of string
  vdc = null
  # vm_ids - (required) is a type of set of string
  vm_ids = []
}
```

[top](#index)

### Variables

```terraform
variable "enabled" {
  description = "(optional) - True if this affinity rule is enabled"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - VM affinity rule name"
  type        = string
}

variable "org" {
  description = "(optional) - The name of organization to use, optional if defined at provider level. Useful when connected as sysadmin working across different organizations"
  type        = string
  default     = null
}

variable "polarity" {
  description = "(required) - One of 'Affinity', 'Anti-Affinity'"
  type        = string
}

variable "required" {
  description = "(optional) - True if this affinity rule is required. When a rule is mandatory, a host failover will not power on the VM if doing so would violate the rule"
  type        = bool
  default     = null
}

variable "vdc" {
  description = "(optional) - The name of VDC to use, optional if defined at provider level"
  type        = string
  default     = null
}

variable "vm_ids" {
  description = "(required) - Set of VM IDs assigned to this rule"
  type        = set(string)
}
```

[top](#index)

### Resource

```terraform
resource "vcd_vm_affinity_rule" "this" {
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # name - (required) is a type of string
  name = var.name
  # org - (optional) is a type of string
  org = var.org
  # polarity - (required) is a type of string
  polarity = var.polarity
  # required - (optional) is a type of bool
  required = var.required
  # vdc - (optional) is a type of string
  vdc = var.vdc
  # vm_ids - (required) is a type of set of string
  vm_ids = var.vm_ids
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vcd_vm_affinity_rule.this.id
}

output "this" {
  value = vcd_vm_affinity_rule.this
}
```

[top](#index)