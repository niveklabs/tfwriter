# aci_node_block_firmware

[back](../aci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aci = ">= 0.5.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aci_node_block_firmware" {
  source = "./modules/aci/r/aci_node_block_firmware"

  # annotation - (optional) is a type of string
  annotation = null
  # description - (optional) is a type of string
  description = null
  # firmware_group_dn - (required) is a type of string
  firmware_group_dn = null
  # from_ - (optional) is a type of string
  from_ = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # to_ - (optional) is a type of string
  to_ = null
}
```

[top](#index)

### Variables

```terraform
variable "annotation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "firmware_group_dn" {
  description = "(required)"
  type        = string
}

variable "from_" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "name_alias" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "to_" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aci_node_block_firmware" "this" {
  annotation        = var.annotation
  description       = var.description
  firmware_group_dn = var.firmware_group_dn
  from_             = var.from_
  name              = var.name
  name_alias        = var.name_alias
  to_               = var.to_
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = aci_node_block_firmware.this.description
}

output "from_" {
  description = "returns a string"
  value       = aci_node_block_firmware.this.from_
}

output "id" {
  description = "returns a string"
  value       = aci_node_block_firmware.this.id
}

output "name_alias" {
  description = "returns a string"
  value       = aci_node_block_firmware.this.name_alias
}

output "to_" {
  description = "returns a string"
  value       = aci_node_block_firmware.this.to_
}

output "this" {
  value = aci_node_block_firmware.this
}
```

[top](#index)