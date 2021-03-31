# aci_end_point_retention_policy

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
module "aci_end_point_retention_policy" {
  source = "./modules/aci/r/aci_end_point_retention_policy"

  # annotation - (optional) is a type of string
  annotation = null
  # bounce_age_intvl - (optional) is a type of string
  bounce_age_intvl = null
  # bounce_trig - (optional) is a type of string
  bounce_trig = null
  # description - (optional) is a type of string
  description = null
  # hold_intvl - (optional) is a type of string
  hold_intvl = null
  # local_ep_age_intvl - (optional) is a type of string
  local_ep_age_intvl = null
  # move_freq - (optional) is a type of string
  move_freq = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # remote_ep_age_intvl - (optional) is a type of string
  remote_ep_age_intvl = null
  # tenant_dn - (required) is a type of string
  tenant_dn = null
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

variable "bounce_age_intvl" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bounce_trig" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hold_intvl" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "local_ep_age_intvl" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "move_freq" {
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

variable "remote_ep_age_intvl" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tenant_dn" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aci_end_point_retention_policy" "this" {
  annotation          = var.annotation
  bounce_age_intvl    = var.bounce_age_intvl
  bounce_trig         = var.bounce_trig
  description         = var.description
  hold_intvl          = var.hold_intvl
  local_ep_age_intvl  = var.local_ep_age_intvl
  move_freq           = var.move_freq
  name                = var.name
  name_alias          = var.name_alias
  remote_ep_age_intvl = var.remote_ep_age_intvl
  tenant_dn           = var.tenant_dn
}
```

[top](#index)

### Outputs

```terraform
output "bounce_age_intvl" {
  description = "returns a string"
  value       = aci_end_point_retention_policy.this.bounce_age_intvl
}

output "bounce_trig" {
  description = "returns a string"
  value       = aci_end_point_retention_policy.this.bounce_trig
}

output "description" {
  description = "returns a string"
  value       = aci_end_point_retention_policy.this.description
}

output "hold_intvl" {
  description = "returns a string"
  value       = aci_end_point_retention_policy.this.hold_intvl
}

output "id" {
  description = "returns a string"
  value       = aci_end_point_retention_policy.this.id
}

output "local_ep_age_intvl" {
  description = "returns a string"
  value       = aci_end_point_retention_policy.this.local_ep_age_intvl
}

output "move_freq" {
  description = "returns a string"
  value       = aci_end_point_retention_policy.this.move_freq
}

output "name_alias" {
  description = "returns a string"
  value       = aci_end_point_retention_policy.this.name_alias
}

output "remote_ep_age_intvl" {
  description = "returns a string"
  value       = aci_end_point_retention_policy.this.remote_ep_age_intvl
}

output "this" {
  value = aci_end_point_retention_policy.this
}
```

[top](#index)