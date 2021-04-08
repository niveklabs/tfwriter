# vcd_vm_affinity_rule

[back](../vcd.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/vcd/d/vcd_vm_affinity_rule"

  # name - (optional) is a type of string
  name = null
  # org - (optional) is a type of string
  org = null
  # rule_id - (optional) is a type of string
  rule_id = null
  # vdc - (optional) is a type of string
  vdc = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - VM affinity rule name. Used to retrieve a rule only when the name is unique"
  type        = string
  default     = null
}

variable "org" {
  description = "(optional) - The name of organization to use, optional if defined at provider level. Useful when connected as sysadmin working across different organizations"
  type        = string
  default     = null
}

variable "rule_id" {
  description = "(optional) - VM affinity rule ID. It's the preferred way of identifying a rule"
  type        = string
  default     = null
}

variable "vdc" {
  description = "(optional) - The name of VDC to use, optional if defined at provider level"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "vcd_vm_affinity_rule" "this" {
  # name - (optional) is a type of string
  name = var.name
  # org - (optional) is a type of string
  org = var.org
  # rule_id - (optional) is a type of string
  rule_id = var.rule_id
  # vdc - (optional) is a type of string
  vdc = var.vdc
}
```

[top](#index)

### Outputs

```terraform
output "enabled" {
  description = "returns a bool"
  value       = data.vcd_vm_affinity_rule.this.enabled
}

output "id" {
  description = "returns a string"
  value       = data.vcd_vm_affinity_rule.this.id
}

output "polarity" {
  description = "returns a string"
  value       = data.vcd_vm_affinity_rule.this.polarity
}

output "required" {
  description = "returns a bool"
  value       = data.vcd_vm_affinity_rule.this.required
}

output "vm_ids" {
  description = "returns a set of string"
  value       = data.vcd_vm_affinity_rule.this.vm_ids
}

output "this" {
  value = vcd_vm_affinity_rule.this
}
```

[top](#index)