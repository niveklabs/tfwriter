# nsxt_policy_vm

[back](../nsxt.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nsxt = ">= 3.1.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nsxt_policy_vm" {
  source = "./modules/nsxt/d/nsxt_policy_vm"

  # bios_id - (optional) is a type of string
  bios_id = null
  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # external_id - (optional) is a type of string
  external_id = null
  # instance_id - (optional) is a type of string
  instance_id = null
}
```

[top](#index)

### Variables

```terraform
variable "bios_id" {
  description = "(optional) - BIOS UUID of the Virtual Machine"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - Description for this resource"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional) - Display name of this resource"
  type        = string
  default     = null
}

variable "external_id" {
  description = "(optional) - External ID of the Virtual Machine"
  type        = string
  default     = null
}

variable "instance_id" {
  description = "(optional) - Instance UUID of the Virtual Machine"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "nsxt_policy_vm" "this" {
  bios_id      = var.bios_id
  description  = var.description
  display_name = var.display_name
  external_id  = var.external_id
  instance_id  = var.instance_id
}
```

[top](#index)

### Outputs

```terraform
output "bios_id" {
  description = "returns a string"
  value       = data.nsxt_policy_vm.this.bios_id
}

output "description" {
  description = "returns a string"
  value       = data.nsxt_policy_vm.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.nsxt_policy_vm.this.display_name
}

output "external_id" {
  description = "returns a string"
  value       = data.nsxt_policy_vm.this.external_id
}

output "id" {
  description = "returns a string"
  value       = data.nsxt_policy_vm.this.id
}

output "instance_id" {
  description = "returns a string"
  value       = data.nsxt_policy_vm.this.instance_id
}

output "this" {
  value = nsxt_policy_vm.this
}
```

[top](#index)