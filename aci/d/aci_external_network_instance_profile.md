# aci_external_network_instance_profile

[back](../aci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "aci_external_network_instance_profile" {
  source = "./modules/aci/d/aci_external_network_instance_profile"

  # annotation - (optional) is a type of string
  annotation = null
  # description - (optional) is a type of string
  description = null
  # exception_tag - (optional) is a type of string
  exception_tag = null
  # flood_on_encap - (optional) is a type of string
  flood_on_encap = null
  # l3_outside_dn - (required) is a type of string
  l3_outside_dn = null
  # match_t - (optional) is a type of string
  match_t = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # pref_gr_memb - (optional) is a type of string
  pref_gr_memb = null
  # prio - (optional) is a type of string
  prio = null
  # target_dscp - (optional) is a type of string
  target_dscp = null
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

variable "exception_tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "flood_on_encap" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "l3_outside_dn" {
  description = "(required)"
  type        = string
}

variable "match_t" {
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

variable "pref_gr_memb" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "prio" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "target_dscp" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aci_external_network_instance_profile" "this" {
  # annotation - (optional) is a type of string
  annotation = var.annotation
  # description - (optional) is a type of string
  description = var.description
  # exception_tag - (optional) is a type of string
  exception_tag = var.exception_tag
  # flood_on_encap - (optional) is a type of string
  flood_on_encap = var.flood_on_encap
  # l3_outside_dn - (required) is a type of string
  l3_outside_dn = var.l3_outside_dn
  # match_t - (optional) is a type of string
  match_t = var.match_t
  # name - (required) is a type of string
  name = var.name
  # name_alias - (optional) is a type of string
  name_alias = var.name_alias
  # pref_gr_memb - (optional) is a type of string
  pref_gr_memb = var.pref_gr_memb
  # prio - (optional) is a type of string
  prio = var.prio
  # target_dscp - (optional) is a type of string
  target_dscp = var.target_dscp
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.aci_external_network_instance_profile.this.description
}

output "exception_tag" {
  description = "returns a string"
  value       = data.aci_external_network_instance_profile.this.exception_tag
}

output "flood_on_encap" {
  description = "returns a string"
  value       = data.aci_external_network_instance_profile.this.flood_on_encap
}

output "id" {
  description = "returns a string"
  value       = data.aci_external_network_instance_profile.this.id
}

output "match_t" {
  description = "returns a string"
  value       = data.aci_external_network_instance_profile.this.match_t
}

output "name_alias" {
  description = "returns a string"
  value       = data.aci_external_network_instance_profile.this.name_alias
}

output "pref_gr_memb" {
  description = "returns a string"
  value       = data.aci_external_network_instance_profile.this.pref_gr_memb
}

output "prio" {
  description = "returns a string"
  value       = data.aci_external_network_instance_profile.this.prio
}

output "target_dscp" {
  description = "returns a string"
  value       = data.aci_external_network_instance_profile.this.target_dscp
}

output "this" {
  value = aci_external_network_instance_profile.this
}
```

[top](#index)