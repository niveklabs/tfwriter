# aci_firmware_group

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
module "aci_firmware_group" {
  source = "./modules/aci/r/aci_firmware_group"

  # annotation - (optional) is a type of string
  annotation = null
  # description - (optional) is a type of string
  description = null
  # firmware_group_type - (optional) is a type of string
  firmware_group_type = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # relation_firmware_rs_fwgrpp - (optional) is a type of string
  relation_firmware_rs_fwgrpp = null
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

variable "firmware_group_type" {
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

variable "relation_firmware_rs_fwgrpp" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aci_firmware_group" "this" {
  annotation                  = var.annotation
  description                 = var.description
  firmware_group_type         = var.firmware_group_type
  name                        = var.name
  name_alias                  = var.name_alias
  relation_firmware_rs_fwgrpp = var.relation_firmware_rs_fwgrpp
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = aci_firmware_group.this.description
}

output "firmware_group_type" {
  description = "returns a string"
  value       = aci_firmware_group.this.firmware_group_type
}

output "id" {
  description = "returns a string"
  value       = aci_firmware_group.this.id
}

output "name_alias" {
  description = "returns a string"
  value       = aci_firmware_group.this.name_alias
}

output "this" {
  value = aci_firmware_group.this
}
```

[top](#index)