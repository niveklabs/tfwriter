# aci_pod_maintenance_group

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
    aci = ">= 0.5.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aci_pod_maintenance_group" {
  source = "./modules/aci/r/aci_pod_maintenance_group"

  # annotation - (optional) is a type of string
  annotation = null
  # description - (optional) is a type of string
  description = null
  # fwtype - (optional) is a type of string
  fwtype = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # pod_maintenance_group_type - (optional) is a type of string
  pod_maintenance_group_type = null
  # relation_maint_rs_mgrpp - (optional) is a type of string
  relation_maint_rs_mgrpp = null
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

variable "fwtype" {
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

variable "pod_maintenance_group_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_maint_rs_mgrpp" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aci_pod_maintenance_group" "this" {
  annotation                 = var.annotation
  description                = var.description
  fwtype                     = var.fwtype
  name                       = var.name
  name_alias                 = var.name_alias
  pod_maintenance_group_type = var.pod_maintenance_group_type
  relation_maint_rs_mgrpp    = var.relation_maint_rs_mgrpp
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = aci_pod_maintenance_group.this.description
}

output "fwtype" {
  description = "returns a string"
  value       = aci_pod_maintenance_group.this.fwtype
}

output "id" {
  description = "returns a string"
  value       = aci_pod_maintenance_group.this.id
}

output "name_alias" {
  description = "returns a string"
  value       = aci_pod_maintenance_group.this.name_alias
}

output "pod_maintenance_group_type" {
  description = "returns a string"
  value       = aci_pod_maintenance_group.this.pod_maintenance_group_type
}

output "this" {
  value = aci_pod_maintenance_group.this
}
```

[top](#index)