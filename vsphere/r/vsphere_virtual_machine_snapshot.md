# vsphere_virtual_machine_snapshot

[back](../vsphere.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vsphere = ">= 1.25.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vsphere_virtual_machine_snapshot" {
  source = "./modules/vsphere/r/vsphere_virtual_machine_snapshot"

  # consolidate - (optional) is a type of bool
  consolidate = null
  # description - (required) is a type of string
  description = null
  # memory - (required) is a type of bool
  memory = null
  # quiesce - (required) is a type of bool
  quiesce = null
  # remove_children - (optional) is a type of bool
  remove_children = null
  # snapshot_name - (required) is a type of string
  snapshot_name = null
  # virtual_machine_uuid - (required) is a type of string
  virtual_machine_uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "consolidate" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "description" {
  description = "(required)"
  type        = string
}

variable "memory" {
  description = "(required)"
  type        = bool
}

variable "quiesce" {
  description = "(required)"
  type        = bool
}

variable "remove_children" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "snapshot_name" {
  description = "(required)"
  type        = string
}

variable "virtual_machine_uuid" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "vsphere_virtual_machine_snapshot" "this" {
  # consolidate - (optional) is a type of bool
  consolidate = var.consolidate
  # description - (required) is a type of string
  description = var.description
  # memory - (required) is a type of bool
  memory = var.memory
  # quiesce - (required) is a type of bool
  quiesce = var.quiesce
  # remove_children - (optional) is a type of bool
  remove_children = var.remove_children
  # snapshot_name - (required) is a type of string
  snapshot_name = var.snapshot_name
  # virtual_machine_uuid - (required) is a type of string
  virtual_machine_uuid = var.virtual_machine_uuid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vsphere_virtual_machine_snapshot.this.id
}

output "this" {
  value = vsphere_virtual_machine_snapshot.this
}
```

[top](#index)