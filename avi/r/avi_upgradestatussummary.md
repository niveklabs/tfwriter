# avi_upgradestatussummary

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
module "avi_upgradestatussummary" {
  source = "./modules/avi/r/avi_upgradestatussummary"

  # enable_patch_rollback - (optional) is a type of bool
  enable_patch_rollback = null
  # enable_rollback - (optional) is a type of bool
  enable_rollback = null
  # end_time - (optional) is a type of string
  end_time = null
  # image_ref - (optional) is a type of string
  image_ref = null
  # name - (optional) is a type of string
  name = null
  # node_type - (optional) is a type of string
  node_type = null
  # obj_cloud_ref - (optional) is a type of string
  obj_cloud_ref = null
  # patch_image_ref - (optional) is a type of string
  patch_image_ref = null
  # start_time - (optional) is a type of string
  start_time = null
  # tasks_completed - (optional) is a type of number
  tasks_completed = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # total_tasks - (optional) is a type of number
  total_tasks = null
  # upgrade_ops - (optional) is a type of string
  upgrade_ops = null
  # uuid - (optional) is a type of string
  uuid = null
  # version - (optional) is a type of string
  version = null

  state = [{
    last_changed_time = [{
      secs  = null
      usecs = null
    }]
    reason = null
    state  = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "enable_patch_rollback" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_rollback" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "end_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "image_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "node_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "obj_cloud_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "patch_image_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "start_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tasks_completed" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "total_tasks" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "upgrade_ops" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "state" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      last_changed_time = set(object(
        {
          secs  = number
          usecs = number
        }
      ))
      reason = string
      state  = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_upgradestatussummary" "this" {
  enable_patch_rollback = var.enable_patch_rollback
  enable_rollback       = var.enable_rollback
  end_time              = var.end_time
  image_ref             = var.image_ref
  name                  = var.name
  node_type             = var.node_type
  obj_cloud_ref         = var.obj_cloud_ref
  patch_image_ref       = var.patch_image_ref
  start_time            = var.start_time
  tasks_completed       = var.tasks_completed
  tenant_ref            = var.tenant_ref
  total_tasks           = var.total_tasks
  upgrade_ops           = var.upgrade_ops
  uuid                  = var.uuid
  version               = var.version

  dynamic "state" {
    for_each = var.state
    content {
      reason = state.value["reason"]
      state  = state.value["state"]

      dynamic "last_changed_time" {
        for_each = state.value.last_changed_time
        content {
          secs  = last_changed_time.value["secs"]
          usecs = last_changed_time.value["usecs"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "end_time" {
  description = "returns a string"
  value       = avi_upgradestatussummary.this.end_time
}

output "id" {
  description = "returns a string"
  value       = avi_upgradestatussummary.this.id
}

output "image_ref" {
  description = "returns a string"
  value       = avi_upgradestatussummary.this.image_ref
}

output "name" {
  description = "returns a string"
  value       = avi_upgradestatussummary.this.name
}

output "node_type" {
  description = "returns a string"
  value       = avi_upgradestatussummary.this.node_type
}

output "obj_cloud_ref" {
  description = "returns a string"
  value       = avi_upgradestatussummary.this.obj_cloud_ref
}

output "patch_image_ref" {
  description = "returns a string"
  value       = avi_upgradestatussummary.this.patch_image_ref
}

output "start_time" {
  description = "returns a string"
  value       = avi_upgradestatussummary.this.start_time
}

output "tasks_completed" {
  description = "returns a number"
  value       = avi_upgradestatussummary.this.tasks_completed
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_upgradestatussummary.this.tenant_ref
}

output "total_tasks" {
  description = "returns a number"
  value       = avi_upgradestatussummary.this.total_tasks
}

output "upgrade_ops" {
  description = "returns a string"
  value       = avi_upgradestatussummary.this.upgrade_ops
}

output "uuid" {
  description = "returns a string"
  value       = avi_upgradestatussummary.this.uuid
}

output "version" {
  description = "returns a string"
  value       = avi_upgradestatussummary.this.version
}

output "this" {
  value = avi_upgradestatussummary.this
}
```

[top](#index)