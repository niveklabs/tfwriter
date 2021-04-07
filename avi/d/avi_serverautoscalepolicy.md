# avi_serverautoscalepolicy

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/avi/d/avi_serverautoscalepolicy"

  # name - (optional) is a type of string
  name = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "avi_serverautoscalepolicy" "this" {
  # name - (optional) is a type of string
  name = var.name
  # tenant_ref - (optional) is a type of string
  tenant_ref = var.tenant_ref
  # uuid - (optional) is a type of string
  uuid = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.avi_serverautoscalepolicy.this.description
}

output "id" {
  description = "returns a string"
  value       = data.avi_serverautoscalepolicy.this.id
}

output "intelligent_autoscale" {
  description = "returns a bool"
  value       = data.avi_serverautoscalepolicy.this.intelligent_autoscale
}

output "intelligent_scalein_margin" {
  description = "returns a number"
  value       = data.avi_serverautoscalepolicy.this.intelligent_scalein_margin
}

output "intelligent_scaleout_margin" {
  description = "returns a number"
  value       = data.avi_serverautoscalepolicy.this.intelligent_scaleout_margin
}

output "max_scalein_adjustment_step" {
  description = "returns a number"
  value       = data.avi_serverautoscalepolicy.this.max_scalein_adjustment_step
}

output "max_scaleout_adjustment_step" {
  description = "returns a number"
  value       = data.avi_serverautoscalepolicy.this.max_scaleout_adjustment_step
}

output "max_size" {
  description = "returns a number"
  value       = data.avi_serverautoscalepolicy.this.max_size
}

output "min_size" {
  description = "returns a number"
  value       = data.avi_serverautoscalepolicy.this.min_size
}

output "name" {
  description = "returns a string"
  value       = data.avi_serverautoscalepolicy.this.name
}

output "scalein_alertconfig_refs" {
  description = "returns a list of string"
  value       = data.avi_serverautoscalepolicy.this.scalein_alertconfig_refs
}

output "scalein_cooldown" {
  description = "returns a number"
  value       = data.avi_serverautoscalepolicy.this.scalein_cooldown
}

output "scaleout_alertconfig_refs" {
  description = "returns a list of string"
  value       = data.avi_serverautoscalepolicy.this.scaleout_alertconfig_refs
}

output "scaleout_cooldown" {
  description = "returns a number"
  value       = data.avi_serverautoscalepolicy.this.scaleout_cooldown
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_serverautoscalepolicy.this.tenant_ref
}

output "use_predicted_load" {
  description = "returns a bool"
  value       = data.avi_serverautoscalepolicy.this.use_predicted_load
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_serverautoscalepolicy.this.uuid
}

output "this" {
  value = avi_serverautoscalepolicy.this
}
```

[top](#index)