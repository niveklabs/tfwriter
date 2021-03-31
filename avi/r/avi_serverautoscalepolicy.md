# avi_serverautoscalepolicy

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    avi = ">= 0.2.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "avi_serverautoscalepolicy" {
  source = "./modules/avi/r/avi_serverautoscalepolicy"

  # description - (optional) is a type of string
  description = null
  # intelligent_autoscale - (optional) is a type of bool
  intelligent_autoscale = null
  # intelligent_scalein_margin - (optional) is a type of number
  intelligent_scalein_margin = null
  # intelligent_scaleout_margin - (optional) is a type of number
  intelligent_scaleout_margin = null
  # max_scalein_adjustment_step - (optional) is a type of number
  max_scalein_adjustment_step = null
  # max_scaleout_adjustment_step - (optional) is a type of number
  max_scaleout_adjustment_step = null
  # max_size - (optional) is a type of number
  max_size = null
  # min_size - (optional) is a type of number
  min_size = null
  # name - (required) is a type of string
  name = null
  # scalein_alertconfig_refs - (optional) is a type of list of string
  scalein_alertconfig_refs = []
  # scalein_cooldown - (optional) is a type of number
  scalein_cooldown = null
  # scaleout_alertconfig_refs - (optional) is a type of list of string
  scaleout_alertconfig_refs = []
  # scaleout_cooldown - (optional) is a type of number
  scaleout_cooldown = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # use_predicted_load - (optional) is a type of bool
  use_predicted_load = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "intelligent_autoscale" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "intelligent_scalein_margin" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "intelligent_scaleout_margin" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_scalein_adjustment_step" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_scaleout_adjustment_step" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "min_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "scalein_alertconfig_refs" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "scalein_cooldown" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "scaleout_alertconfig_refs" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "scaleout_cooldown" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "use_predicted_load" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "avi_serverautoscalepolicy" "this" {
  description                  = var.description
  intelligent_autoscale        = var.intelligent_autoscale
  intelligent_scalein_margin   = var.intelligent_scalein_margin
  intelligent_scaleout_margin  = var.intelligent_scaleout_margin
  max_scalein_adjustment_step  = var.max_scalein_adjustment_step
  max_scaleout_adjustment_step = var.max_scaleout_adjustment_step
  max_size                     = var.max_size
  min_size                     = var.min_size
  name                         = var.name
  scalein_alertconfig_refs     = var.scalein_alertconfig_refs
  scalein_cooldown             = var.scalein_cooldown
  scaleout_alertconfig_refs    = var.scaleout_alertconfig_refs
  scaleout_cooldown            = var.scaleout_cooldown
  tenant_ref                   = var.tenant_ref
  use_predicted_load           = var.use_predicted_load
  uuid                         = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = avi_serverautoscalepolicy.this.description
}

output "id" {
  description = "returns a string"
  value       = avi_serverautoscalepolicy.this.id
}

output "max_size" {
  description = "returns a number"
  value       = avi_serverautoscalepolicy.this.max_size
}

output "min_size" {
  description = "returns a number"
  value       = avi_serverautoscalepolicy.this.min_size
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_serverautoscalepolicy.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_serverautoscalepolicy.this.uuid
}

output "this" {
  value = avi_serverautoscalepolicy.this
}
```

[top](#index)