# avi_alertconfig

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
module "avi_alertconfig" {
  source = "./modules/avi/d/avi_alertconfig"

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
data "avi_alertconfig" "this" {
  name       = var.name
  tenant_ref = var.tenant_ref
  uuid       = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "action_group_ref" {
  description = "returns a string"
  value       = data.avi_alertconfig.this.action_group_ref
}

output "alert_rule" {
  description = "returns a set of object"
  value       = data.avi_alertconfig.this.alert_rule
}

output "autoscale_alert" {
  description = "returns a bool"
  value       = data.avi_alertconfig.this.autoscale_alert
}

output "category" {
  description = "returns a string"
  value       = data.avi_alertconfig.this.category
}

output "description" {
  description = "returns a string"
  value       = data.avi_alertconfig.this.description
}

output "enabled" {
  description = "returns a bool"
  value       = data.avi_alertconfig.this.enabled
}

output "expiry_time" {
  description = "returns a number"
  value       = data.avi_alertconfig.this.expiry_time
}

output "id" {
  description = "returns a string"
  value       = data.avi_alertconfig.this.id
}

output "name" {
  description = "returns a string"
  value       = data.avi_alertconfig.this.name
}

output "obj_uuid" {
  description = "returns a string"
  value       = data.avi_alertconfig.this.obj_uuid
}

output "object_type" {
  description = "returns a string"
  value       = data.avi_alertconfig.this.object_type
}

output "recommendation" {
  description = "returns a string"
  value       = data.avi_alertconfig.this.recommendation
}

output "rolling_window" {
  description = "returns a number"
  value       = data.avi_alertconfig.this.rolling_window
}

output "source" {
  description = "returns a string"
  value       = data.avi_alertconfig.this.source
}

output "summary" {
  description = "returns a string"
  value       = data.avi_alertconfig.this.summary
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_alertconfig.this.tenant_ref
}

output "threshold" {
  description = "returns a number"
  value       = data.avi_alertconfig.this.threshold
}

output "throttle" {
  description = "returns a number"
  value       = data.avi_alertconfig.this.throttle
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_alertconfig.this.uuid
}

output "this" {
  value = avi_alertconfig.this
}
```

[top](#index)