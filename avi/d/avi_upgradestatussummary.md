# avi_upgradestatussummary

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
module "avi_upgradestatussummary" {
  source = "./modules/avi/d/avi_upgradestatussummary"

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
data "avi_upgradestatussummary" "this" {
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
output "enable_patch_rollback" {
  description = "returns a bool"
  value       = data.avi_upgradestatussummary.this.enable_patch_rollback
}

output "enable_rollback" {
  description = "returns a bool"
  value       = data.avi_upgradestatussummary.this.enable_rollback
}

output "end_time" {
  description = "returns a string"
  value       = data.avi_upgradestatussummary.this.end_time
}

output "id" {
  description = "returns a string"
  value       = data.avi_upgradestatussummary.this.id
}

output "image_ref" {
  description = "returns a string"
  value       = data.avi_upgradestatussummary.this.image_ref
}

output "name" {
  description = "returns a string"
  value       = data.avi_upgradestatussummary.this.name
}

output "node_type" {
  description = "returns a string"
  value       = data.avi_upgradestatussummary.this.node_type
}

output "obj_cloud_ref" {
  description = "returns a string"
  value       = data.avi_upgradestatussummary.this.obj_cloud_ref
}

output "patch_image_ref" {
  description = "returns a string"
  value       = data.avi_upgradestatussummary.this.patch_image_ref
}

output "start_time" {
  description = "returns a string"
  value       = data.avi_upgradestatussummary.this.start_time
}

output "state" {
  description = "returns a set of object"
  value       = data.avi_upgradestatussummary.this.state
}

output "tasks_completed" {
  description = "returns a number"
  value       = data.avi_upgradestatussummary.this.tasks_completed
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_upgradestatussummary.this.tenant_ref
}

output "total_tasks" {
  description = "returns a number"
  value       = data.avi_upgradestatussummary.this.total_tasks
}

output "upgrade_ops" {
  description = "returns a string"
  value       = data.avi_upgradestatussummary.this.upgrade_ops
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_upgradestatussummary.this.uuid
}

output "version" {
  description = "returns a string"
  value       = data.avi_upgradestatussummary.this.version
}

output "this" {
  value = avi_upgradestatussummary.this
}
```

[top](#index)