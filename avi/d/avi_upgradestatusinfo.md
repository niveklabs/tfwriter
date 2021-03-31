# avi_upgradestatusinfo

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
module "avi_upgradestatusinfo" {
  source = "./modules/avi/d/avi_upgradestatusinfo"

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
data "avi_upgradestatusinfo" "this" {
  name       = var.name
  tenant_ref = var.tenant_ref
  uuid       = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "duration" {
  description = "returns a number"
  value       = data.avi_upgradestatusinfo.this.duration
}

output "enable_patch_rollback" {
  description = "returns a bool"
  value       = data.avi_upgradestatusinfo.this.enable_patch_rollback
}

output "enable_rollback" {
  description = "returns a bool"
  value       = data.avi_upgradestatusinfo.this.enable_rollback
}

output "end_time" {
  description = "returns a string"
  value       = data.avi_upgradestatusinfo.this.end_time
}

output "enqueue_time" {
  description = "returns a string"
  value       = data.avi_upgradestatusinfo.this.enqueue_time
}

output "id" {
  description = "returns a string"
  value       = data.avi_upgradestatusinfo.this.id
}

output "image_ref" {
  description = "returns a string"
  value       = data.avi_upgradestatusinfo.this.image_ref
}

output "name" {
  description = "returns a string"
  value       = data.avi_upgradestatusinfo.this.name
}

output "node_type" {
  description = "returns a string"
  value       = data.avi_upgradestatusinfo.this.node_type
}

output "obj_cloud_ref" {
  description = "returns a string"
  value       = data.avi_upgradestatusinfo.this.obj_cloud_ref
}

output "params" {
  description = "returns a set of object"
  value       = data.avi_upgradestatusinfo.this.params
}

output "patch_image_ref" {
  description = "returns a string"
  value       = data.avi_upgradestatusinfo.this.patch_image_ref
}

output "patch_list" {
  description = "returns a list of object"
  value       = data.avi_upgradestatusinfo.this.patch_list
}

output "patch_version" {
  description = "returns a string"
  value       = data.avi_upgradestatusinfo.this.patch_version
}

output "previous_image_ref" {
  description = "returns a string"
  value       = data.avi_upgradestatusinfo.this.previous_image_ref
}

output "previous_patch_image_ref" {
  description = "returns a string"
  value       = data.avi_upgradestatusinfo.this.previous_patch_image_ref
}

output "previous_patch_list" {
  description = "returns a list of object"
  value       = data.avi_upgradestatusinfo.this.previous_patch_list
}

output "previous_patch_version" {
  description = "returns a string"
  value       = data.avi_upgradestatusinfo.this.previous_patch_version
}

output "previous_version" {
  description = "returns a string"
  value       = data.avi_upgradestatusinfo.this.previous_version
}

output "progress" {
  description = "returns a number"
  value       = data.avi_upgradestatusinfo.this.progress
}

output "se_upgrade_events" {
  description = "returns a list of object"
  value       = data.avi_upgradestatusinfo.this.se_upgrade_events
}

output "seg_status" {
  description = "returns a set of object"
  value       = data.avi_upgradestatusinfo.this.seg_status
}

output "start_time" {
  description = "returns a string"
  value       = data.avi_upgradestatusinfo.this.start_time
}

output "state" {
  description = "returns a set of object"
  value       = data.avi_upgradestatusinfo.this.state
}

output "system" {
  description = "returns a bool"
  value       = data.avi_upgradestatusinfo.this.system
}

output "tasks_completed" {
  description = "returns a number"
  value       = data.avi_upgradestatusinfo.this.tasks_completed
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_upgradestatusinfo.this.tenant_ref
}

output "total_tasks" {
  description = "returns a number"
  value       = data.avi_upgradestatusinfo.this.total_tasks
}

output "upgrade_events" {
  description = "returns a list of object"
  value       = data.avi_upgradestatusinfo.this.upgrade_events
}

output "upgrade_ops" {
  description = "returns a string"
  value       = data.avi_upgradestatusinfo.this.upgrade_ops
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_upgradestatusinfo.this.uuid
}

output "version" {
  description = "returns a string"
  value       = data.avi_upgradestatusinfo.this.version
}

output "this" {
  value = avi_upgradestatusinfo.this
}
```

[top](#index)