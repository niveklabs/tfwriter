# mso_schema_template_bd

[back](../mso.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    mso = ">= 0.1.5"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "mso_schema_template_bd" {
  source = "./modules/mso/d/mso_schema_template_bd"

  # dhcp_policy - (optional) is a type of map of string
  dhcp_policy = {}
  # display_name - (optional) is a type of string
  display_name = null
  # intersite_bum_traffic - (optional) is a type of bool
  intersite_bum_traffic = null
  # layer2_stretch - (optional) is a type of bool
  layer2_stretch = null
  # layer2_unknown_unicast - (optional) is a type of string
  layer2_unknown_unicast = null
  # layer3_multicast - (optional) is a type of bool
  layer3_multicast = null
  # name - (required) is a type of string
  name = null
  # optimize_wan_bandwidth - (optional) is a type of bool
  optimize_wan_bandwidth = null
  # schema_id - (required) is a type of string
  schema_id = null
  # template_name - (required) is a type of string
  template_name = null
  # vrf_name - (optional) is a type of string
  vrf_name = null
  # vrf_schema_id - (optional) is a type of string
  vrf_schema_id = null
  # vrf_template_name - (optional) is a type of string
  vrf_template_name = null
}
```

[top](#index)

### Variables

```terraform
variable "dhcp_policy" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "intersite_bum_traffic" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "layer2_stretch" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "layer2_unknown_unicast" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "layer3_multicast" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "optimize_wan_bandwidth" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "schema_id" {
  description = "(required)"
  type        = string
}

variable "template_name" {
  description = "(required)"
  type        = string
}

variable "vrf_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vrf_schema_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vrf_template_name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "mso_schema_template_bd" "this" {
  # dhcp_policy - (optional) is a type of map of string
  dhcp_policy = var.dhcp_policy
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # intersite_bum_traffic - (optional) is a type of bool
  intersite_bum_traffic = var.intersite_bum_traffic
  # layer2_stretch - (optional) is a type of bool
  layer2_stretch = var.layer2_stretch
  # layer2_unknown_unicast - (optional) is a type of string
  layer2_unknown_unicast = var.layer2_unknown_unicast
  # layer3_multicast - (optional) is a type of bool
  layer3_multicast = var.layer3_multicast
  # name - (required) is a type of string
  name = var.name
  # optimize_wan_bandwidth - (optional) is a type of bool
  optimize_wan_bandwidth = var.optimize_wan_bandwidth
  # schema_id - (required) is a type of string
  schema_id = var.schema_id
  # template_name - (required) is a type of string
  template_name = var.template_name
  # vrf_name - (optional) is a type of string
  vrf_name = var.vrf_name
  # vrf_schema_id - (optional) is a type of string
  vrf_schema_id = var.vrf_schema_id
  # vrf_template_name - (optional) is a type of string
  vrf_template_name = var.vrf_template_name
}
```

[top](#index)

### Outputs

```terraform
output "dhcp_policy" {
  description = "returns a map of string"
  value       = data.mso_schema_template_bd.this.dhcp_policy
}

output "display_name" {
  description = "returns a string"
  value       = data.mso_schema_template_bd.this.display_name
}

output "id" {
  description = "returns a string"
  value       = data.mso_schema_template_bd.this.id
}

output "intersite_bum_traffic" {
  description = "returns a bool"
  value       = data.mso_schema_template_bd.this.intersite_bum_traffic
}

output "layer2_stretch" {
  description = "returns a bool"
  value       = data.mso_schema_template_bd.this.layer2_stretch
}

output "layer2_unknown_unicast" {
  description = "returns a string"
  value       = data.mso_schema_template_bd.this.layer2_unknown_unicast
}

output "layer3_multicast" {
  description = "returns a bool"
  value       = data.mso_schema_template_bd.this.layer3_multicast
}

output "optimize_wan_bandwidth" {
  description = "returns a bool"
  value       = data.mso_schema_template_bd.this.optimize_wan_bandwidth
}

output "vrf_name" {
  description = "returns a string"
  value       = data.mso_schema_template_bd.this.vrf_name
}

output "vrf_schema_id" {
  description = "returns a string"
  value       = data.mso_schema_template_bd.this.vrf_schema_id
}

output "vrf_template_name" {
  description = "returns a string"
  value       = data.mso_schema_template_bd.this.vrf_template_name
}

output "this" {
  value = mso_schema_template_bd.this
}
```

[top](#index)