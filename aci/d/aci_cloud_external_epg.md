# aci_cloud_external_epg

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
    aci = ">= 0.5.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aci_cloud_external_epg" {
  source = "./modules/aci/d/aci_cloud_external_epg"

  # annotation - (optional) is a type of string
  annotation = null
  # cloud_applicationcontainer_dn - (required) is a type of string
  cloud_applicationcontainer_dn = null
  # description - (optional) is a type of string
  description = null
  # exception_tag - (optional) is a type of string
  exception_tag = null
  # flood_on_encap - (optional) is a type of string
  flood_on_encap = null
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
  # route_reachability - (optional) is a type of string
  route_reachability = null
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

variable "cloud_applicationcontainer_dn" {
  description = "(required)"
  type        = string
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

variable "route_reachability" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aci_cloud_external_epg" "this" {
  annotation                    = var.annotation
  cloud_applicationcontainer_dn = var.cloud_applicationcontainer_dn
  description                   = var.description
  exception_tag                 = var.exception_tag
  flood_on_encap                = var.flood_on_encap
  match_t                       = var.match_t
  name                          = var.name
  name_alias                    = var.name_alias
  pref_gr_memb                  = var.pref_gr_memb
  prio                          = var.prio
  route_reachability            = var.route_reachability
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.aci_cloud_external_epg.this.description
}

output "exception_tag" {
  description = "returns a string"
  value       = data.aci_cloud_external_epg.this.exception_tag
}

output "flood_on_encap" {
  description = "returns a string"
  value       = data.aci_cloud_external_epg.this.flood_on_encap
}

output "id" {
  description = "returns a string"
  value       = data.aci_cloud_external_epg.this.id
}

output "match_t" {
  description = "returns a string"
  value       = data.aci_cloud_external_epg.this.match_t
}

output "name_alias" {
  description = "returns a string"
  value       = data.aci_cloud_external_epg.this.name_alias
}

output "pref_gr_memb" {
  description = "returns a string"
  value       = data.aci_cloud_external_epg.this.pref_gr_memb
}

output "prio" {
  description = "returns a string"
  value       = data.aci_cloud_external_epg.this.prio
}

output "route_reachability" {
  description = "returns a string"
  value       = data.aci_cloud_external_epg.this.route_reachability
}

output "this" {
  value = aci_cloud_external_epg.this
}
```

[top](#index)