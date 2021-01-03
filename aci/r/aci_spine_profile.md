# aci_spine_profile

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
module "aci_spine_profile" {
  source = "./modules/aci/r/aci_spine_profile"

  # annotation - (optional) is a type of string
  annotation = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # relation_infra_rs_sp_acc_port_p - (optional) is a type of set of string
  relation_infra_rs_sp_acc_port_p = []
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

variable "name" {
  description = "(required)"
  type        = string
}

variable "name_alias" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "relation_infra_rs_sp_acc_port_p" {
  description = "(optional)"
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aci_spine_profile" "this" {
  annotation                      = var.annotation
  description                     = var.description
  name                            = var.name
  name_alias                      = var.name_alias
  relation_infra_rs_sp_acc_port_p = var.relation_infra_rs_sp_acc_port_p
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = aci_spine_profile.this.description
}

output "id" {
  description = "returns a string"
  value       = aci_spine_profile.this.id
}

output "name_alias" {
  description = "returns a string"
  value       = aci_spine_profile.this.name_alias
}

output "relation_infra_rs_sp_acc_port_p" {
  description = "returns a set of string"
  value       = aci_spine_profile.this.relation_infra_rs_sp_acc_port_p
}

output "this" {
  value = aci_spine_profile.this
}
```

[top](#index)