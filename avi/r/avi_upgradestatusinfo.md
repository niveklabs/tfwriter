# avi_upgradestatusinfo

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
module "avi_upgradestatusinfo" {
  source = "./modules/avi/r/avi_upgradestatusinfo"

  # duration - (optional) is a type of number
  duration = null
  # enable_patch_rollback - (optional) is a type of bool
  enable_patch_rollback = null
  # enable_rollback - (optional) is a type of bool
  enable_rollback = null
  # end_time - (optional) is a type of string
  end_time = null
  # enqueue_time - (optional) is a type of string
  enqueue_time = null
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
  # patch_version - (optional) is a type of string
  patch_version = null
  # previous_image_ref - (optional) is a type of string
  previous_image_ref = null
  # previous_patch_image_ref - (optional) is a type of string
  previous_patch_image_ref = null
  # previous_patch_version - (optional) is a type of string
  previous_patch_version = null
  # previous_version - (optional) is a type of string
  previous_version = null
  # progress - (optional) is a type of number
  progress = null
  # start_time - (optional) is a type of string
  start_time = null
  # system - (optional) is a type of bool
  system = null
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

  params = [{
    image_ref = null
    patch_ref = null
    se_group_options = [{
      action_on_error = null
      disruptive      = null
    }]
    se_group_resume_options = [{
      action_on_error = null
      disruptive      = null
      skip_suspended  = null
    }]
  }]

  patch_list = [{
    patch_image_ref = null
    patch_version   = null
  }]

  previous_patch_list = [{
    patch_image_ref = null
    patch_version   = null
  }]

  se_upgrade_events = [{
    from_se_ref      = null
    num_se           = null
    num_se_group     = null
    num_vs           = null
    reason           = []
    se_group_ha_mode = null
    se_group_ref     = null
    se_ref           = null
    task             = null
    to_se_ref        = null
    traffic_status   = null
    vs_ref           = null
  }]

  seg_status = [{
    controller_version           = null
    disrupted_vs_ref             = []
    duration                     = null
    end_time                     = null
    enqueue_time                 = null
    ha_mode                      = null
    in_progress                  = null
    notes                        = []
    num_se                       = null
    num_se_with_no_vs            = null
    num_se_with_vs_not_scaledout = null
    num_se_with_vs_scaledout     = null
    num_vs                       = null
    num_vs_disrupted             = null
    progress                     = null
    reason                       = []
    request_time                 = null
    se_already_upgraded_at_start = []
    se_disconnected_at_start     = []
    se_group_name                = null
    se_group_uuid                = null
    se_ip_missing_at_start       = []
    se_poweredoff_at_start       = []
    se_reboot_in_progress_ref    = null
    se_upgrade_completed         = []
    se_upgrade_errors = [{
      from_se_ref      = null
      num_se           = null
      num_se_group     = null
      num_vs           = null
      reason           = []
      se_group_ha_mode = null
      se_group_ref     = null
      se_ref           = null
      task             = null
      to_se_ref        = null
      traffic_status   = null
      vs_ref           = null
    }]
    se_upgrade_failed         = []
    se_upgrade_in_progress    = []
    se_upgrade_not_started    = []
    se_upgrade_skip_suspended = []
    se_upgrade_suspended      = []
    se_with_no_vs             = []
    se_with_vs_not_scaledout  = []
    se_with_vs_scaledout      = []
    start_time                = null
    state                     = null
    tenant_ref                = null
    thread                    = null
    traffic_status            = null
    vs_errors = [{
      reason           = []
      se_group_ha_mode = null
      se_group_ref     = null
      tenant_ref       = null
      traffic_status   = null
      vip_id           = null
      vs_ref           = null
    }]
    vs_migrate_in_progress_ref  = []
    vs_scalein_in_progress_ref  = []
    vs_scaleout_in_progress_ref = []
    worker                      = null
  }]

  state = [{
    last_changed_time = [{
      secs  = null
      usecs = null
    }]
    reason = null
    state  = null
  }]

  upgrade_events = [{
    nodes_events = [{
      duration = null
      end_time = null
      ip = [{
        addr = null
        type = null
      }]
      message    = null
      start_time = null
      status     = null
      sub_tasks  = []
    }]
    task = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "duration" {
  description = "(optional)"
  type        = number
  default     = null
}

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

variable "enqueue_time" {
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

variable "patch_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "previous_image_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "previous_patch_image_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "previous_patch_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "previous_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "progress" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "start_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "system" {
  description = "(optional)"
  type        = bool
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

variable "params" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      image_ref = string
      patch_ref = string
      se_group_options = set(object(
        {
          action_on_error = string
          disruptive      = bool
        }
      ))
      se_group_resume_options = set(object(
        {
          action_on_error = string
          disruptive      = bool
          skip_suspended  = bool
        }
      ))
    }
  ))
  default = []
}

variable "patch_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      patch_image_ref = string
      patch_version   = string
    }
  ))
  default = []
}

variable "previous_patch_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      patch_image_ref = string
      patch_version   = string
    }
  ))
  default = []
}

variable "se_upgrade_events" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      from_se_ref      = string
      num_se           = number
      num_se_group     = number
      num_vs           = number
      reason           = list(string)
      se_group_ha_mode = string
      se_group_ref     = string
      se_ref           = string
      task             = string
      to_se_ref        = string
      traffic_status   = string
      vs_ref           = string
    }
  ))
  default = []
}

variable "seg_status" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      controller_version           = string
      disrupted_vs_ref             = list(string)
      duration                     = string
      end_time                     = string
      enqueue_time                 = string
      ha_mode                      = string
      in_progress                  = bool
      notes                        = list(string)
      num_se                       = number
      num_se_with_no_vs            = number
      num_se_with_vs_not_scaledout = number
      num_se_with_vs_scaledout     = number
      num_vs                       = number
      num_vs_disrupted             = number
      progress                     = number
      reason                       = list(string)
      request_time                 = string
      se_already_upgraded_at_start = list(string)
      se_disconnected_at_start     = list(string)
      se_group_name                = string
      se_group_uuid                = string
      se_ip_missing_at_start       = list(string)
      se_poweredoff_at_start       = list(string)
      se_reboot_in_progress_ref    = string
      se_upgrade_completed         = list(string)
      se_upgrade_errors = list(object(
        {
          from_se_ref      = string
          num_se           = number
          num_se_group     = number
          num_vs           = number
          reason           = list(string)
          se_group_ha_mode = string
          se_group_ref     = string
          se_ref           = string
          task             = string
          to_se_ref        = string
          traffic_status   = string
          vs_ref           = string
        }
      ))
      se_upgrade_failed         = list(string)
      se_upgrade_in_progress    = list(string)
      se_upgrade_not_started    = list(string)
      se_upgrade_skip_suspended = list(string)
      se_upgrade_suspended      = list(string)
      se_with_no_vs             = list(string)
      se_with_vs_not_scaledout  = list(string)
      se_with_vs_scaledout      = list(string)
      start_time                = string
      state                     = string
      tenant_ref                = string
      thread                    = string
      traffic_status            = string
      vs_errors = list(object(
        {
          reason           = list(string)
          se_group_ha_mode = string
          se_group_ref     = string
          tenant_ref       = string
          traffic_status   = string
          vip_id           = string
          vs_ref           = string
        }
      ))
      vs_migrate_in_progress_ref  = list(string)
      vs_scalein_in_progress_ref  = list(string)
      vs_scaleout_in_progress_ref = list(string)
      worker                      = string
    }
  ))
  default = []
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

variable "upgrade_events" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      nodes_events = list(object(
        {
          duration = number
          end_time = string
          ip = set(object(
            {
              addr = string
              type = string
            }
          ))
          message    = string
          start_time = string
          status     = bool
          sub_tasks  = list(string)
        }
      ))
      task = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_upgradestatusinfo" "this" {
  duration                 = var.duration
  enable_patch_rollback    = var.enable_patch_rollback
  enable_rollback          = var.enable_rollback
  end_time                 = var.end_time
  enqueue_time             = var.enqueue_time
  image_ref                = var.image_ref
  name                     = var.name
  node_type                = var.node_type
  obj_cloud_ref            = var.obj_cloud_ref
  patch_image_ref          = var.patch_image_ref
  patch_version            = var.patch_version
  previous_image_ref       = var.previous_image_ref
  previous_patch_image_ref = var.previous_patch_image_ref
  previous_patch_version   = var.previous_patch_version
  previous_version         = var.previous_version
  progress                 = var.progress
  start_time               = var.start_time
  system                   = var.system
  tasks_completed          = var.tasks_completed
  tenant_ref               = var.tenant_ref
  total_tasks              = var.total_tasks
  upgrade_ops              = var.upgrade_ops
  uuid                     = var.uuid
  version                  = var.version

  dynamic "params" {
    for_each = var.params
    content {
      image_ref = params.value["image_ref"]
      patch_ref = params.value["patch_ref"]

      dynamic "se_group_options" {
        for_each = params.value.se_group_options
        content {
          action_on_error = se_group_options.value["action_on_error"]
          disruptive      = se_group_options.value["disruptive"]
        }
      }

      dynamic "se_group_resume_options" {
        for_each = params.value.se_group_resume_options
        content {
          action_on_error = se_group_resume_options.value["action_on_error"]
          disruptive      = se_group_resume_options.value["disruptive"]
          skip_suspended  = se_group_resume_options.value["skip_suspended"]
        }
      }

    }
  }

  dynamic "patch_list" {
    for_each = var.patch_list
    content {
      patch_image_ref = patch_list.value["patch_image_ref"]
      patch_version   = patch_list.value["patch_version"]
    }
  }

  dynamic "previous_patch_list" {
    for_each = var.previous_patch_list
    content {
      patch_image_ref = previous_patch_list.value["patch_image_ref"]
      patch_version   = previous_patch_list.value["patch_version"]
    }
  }

  dynamic "se_upgrade_events" {
    for_each = var.se_upgrade_events
    content {
      from_se_ref      = se_upgrade_events.value["from_se_ref"]
      num_se           = se_upgrade_events.value["num_se"]
      num_se_group     = se_upgrade_events.value["num_se_group"]
      num_vs           = se_upgrade_events.value["num_vs"]
      reason           = se_upgrade_events.value["reason"]
      se_group_ha_mode = se_upgrade_events.value["se_group_ha_mode"]
      se_group_ref     = se_upgrade_events.value["se_group_ref"]
      se_ref           = se_upgrade_events.value["se_ref"]
      task             = se_upgrade_events.value["task"]
      to_se_ref        = se_upgrade_events.value["to_se_ref"]
      traffic_status   = se_upgrade_events.value["traffic_status"]
      vs_ref           = se_upgrade_events.value["vs_ref"]
    }
  }

  dynamic "seg_status" {
    for_each = var.seg_status
    content {
      controller_version           = seg_status.value["controller_version"]
      disrupted_vs_ref             = seg_status.value["disrupted_vs_ref"]
      duration                     = seg_status.value["duration"]
      end_time                     = seg_status.value["end_time"]
      enqueue_time                 = seg_status.value["enqueue_time"]
      ha_mode                      = seg_status.value["ha_mode"]
      in_progress                  = seg_status.value["in_progress"]
      notes                        = seg_status.value["notes"]
      num_se                       = seg_status.value["num_se"]
      num_se_with_no_vs            = seg_status.value["num_se_with_no_vs"]
      num_se_with_vs_not_scaledout = seg_status.value["num_se_with_vs_not_scaledout"]
      num_se_with_vs_scaledout     = seg_status.value["num_se_with_vs_scaledout"]
      num_vs                       = seg_status.value["num_vs"]
      num_vs_disrupted             = seg_status.value["num_vs_disrupted"]
      progress                     = seg_status.value["progress"]
      reason                       = seg_status.value["reason"]
      request_time                 = seg_status.value["request_time"]
      se_already_upgraded_at_start = seg_status.value["se_already_upgraded_at_start"]
      se_disconnected_at_start     = seg_status.value["se_disconnected_at_start"]
      se_group_name                = seg_status.value["se_group_name"]
      se_group_uuid                = seg_status.value["se_group_uuid"]
      se_ip_missing_at_start       = seg_status.value["se_ip_missing_at_start"]
      se_poweredoff_at_start       = seg_status.value["se_poweredoff_at_start"]
      se_reboot_in_progress_ref    = seg_status.value["se_reboot_in_progress_ref"]
      se_upgrade_completed         = seg_status.value["se_upgrade_completed"]
      se_upgrade_failed            = seg_status.value["se_upgrade_failed"]
      se_upgrade_in_progress       = seg_status.value["se_upgrade_in_progress"]
      se_upgrade_not_started       = seg_status.value["se_upgrade_not_started"]
      se_upgrade_skip_suspended    = seg_status.value["se_upgrade_skip_suspended"]
      se_upgrade_suspended         = seg_status.value["se_upgrade_suspended"]
      se_with_no_vs                = seg_status.value["se_with_no_vs"]
      se_with_vs_not_scaledout     = seg_status.value["se_with_vs_not_scaledout"]
      se_with_vs_scaledout         = seg_status.value["se_with_vs_scaledout"]
      start_time                   = seg_status.value["start_time"]
      state                        = seg_status.value["state"]
      tenant_ref                   = seg_status.value["tenant_ref"]
      thread                       = seg_status.value["thread"]
      traffic_status               = seg_status.value["traffic_status"]
      vs_migrate_in_progress_ref   = seg_status.value["vs_migrate_in_progress_ref"]
      vs_scalein_in_progress_ref   = seg_status.value["vs_scalein_in_progress_ref"]
      vs_scaleout_in_progress_ref  = seg_status.value["vs_scaleout_in_progress_ref"]
      worker                       = seg_status.value["worker"]

      dynamic "se_upgrade_errors" {
        for_each = seg_status.value.se_upgrade_errors
        content {
          from_se_ref      = se_upgrade_errors.value["from_se_ref"]
          num_se           = se_upgrade_errors.value["num_se"]
          num_se_group     = se_upgrade_errors.value["num_se_group"]
          num_vs           = se_upgrade_errors.value["num_vs"]
          reason           = se_upgrade_errors.value["reason"]
          se_group_ha_mode = se_upgrade_errors.value["se_group_ha_mode"]
          se_group_ref     = se_upgrade_errors.value["se_group_ref"]
          se_ref           = se_upgrade_errors.value["se_ref"]
          task             = se_upgrade_errors.value["task"]
          to_se_ref        = se_upgrade_errors.value["to_se_ref"]
          traffic_status   = se_upgrade_errors.value["traffic_status"]
          vs_ref           = se_upgrade_errors.value["vs_ref"]
        }
      }

      dynamic "vs_errors" {
        for_each = seg_status.value.vs_errors
        content {
          reason           = vs_errors.value["reason"]
          se_group_ha_mode = vs_errors.value["se_group_ha_mode"]
          se_group_ref     = vs_errors.value["se_group_ref"]
          tenant_ref       = vs_errors.value["tenant_ref"]
          traffic_status   = vs_errors.value["traffic_status"]
          vip_id           = vs_errors.value["vip_id"]
          vs_ref           = vs_errors.value["vs_ref"]
        }
      }

    }
  }

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

  dynamic "upgrade_events" {
    for_each = var.upgrade_events
    content {
      task = upgrade_events.value["task"]

      dynamic "nodes_events" {
        for_each = upgrade_events.value.nodes_events
        content {
          duration   = nodes_events.value["duration"]
          end_time   = nodes_events.value["end_time"]
          message    = nodes_events.value["message"]
          start_time = nodes_events.value["start_time"]
          status     = nodes_events.value["status"]
          sub_tasks  = nodes_events.value["sub_tasks"]

          dynamic "ip" {
            for_each = nodes_events.value.ip
            content {
              addr = ip.value["addr"]
              type = ip.value["type"]
            }
          }

        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "duration" {
  description = "returns a number"
  value       = avi_upgradestatusinfo.this.duration
}

output "end_time" {
  description = "returns a string"
  value       = avi_upgradestatusinfo.this.end_time
}

output "enqueue_time" {
  description = "returns a string"
  value       = avi_upgradestatusinfo.this.enqueue_time
}

output "id" {
  description = "returns a string"
  value       = avi_upgradestatusinfo.this.id
}

output "image_ref" {
  description = "returns a string"
  value       = avi_upgradestatusinfo.this.image_ref
}

output "name" {
  description = "returns a string"
  value       = avi_upgradestatusinfo.this.name
}

output "node_type" {
  description = "returns a string"
  value       = avi_upgradestatusinfo.this.node_type
}

output "obj_cloud_ref" {
  description = "returns a string"
  value       = avi_upgradestatusinfo.this.obj_cloud_ref
}

output "patch_image_ref" {
  description = "returns a string"
  value       = avi_upgradestatusinfo.this.patch_image_ref
}

output "patch_version" {
  description = "returns a string"
  value       = avi_upgradestatusinfo.this.patch_version
}

output "previous_image_ref" {
  description = "returns a string"
  value       = avi_upgradestatusinfo.this.previous_image_ref
}

output "previous_patch_image_ref" {
  description = "returns a string"
  value       = avi_upgradestatusinfo.this.previous_patch_image_ref
}

output "previous_patch_version" {
  description = "returns a string"
  value       = avi_upgradestatusinfo.this.previous_patch_version
}

output "previous_version" {
  description = "returns a string"
  value       = avi_upgradestatusinfo.this.previous_version
}

output "start_time" {
  description = "returns a string"
  value       = avi_upgradestatusinfo.this.start_time
}

output "system" {
  description = "returns a bool"
  value       = avi_upgradestatusinfo.this.system
}

output "tasks_completed" {
  description = "returns a number"
  value       = avi_upgradestatusinfo.this.tasks_completed
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_upgradestatusinfo.this.tenant_ref
}

output "total_tasks" {
  description = "returns a number"
  value       = avi_upgradestatusinfo.this.total_tasks
}

output "upgrade_ops" {
  description = "returns a string"
  value       = avi_upgradestatusinfo.this.upgrade_ops
}

output "uuid" {
  description = "returns a string"
  value       = avi_upgradestatusinfo.this.uuid
}

output "version" {
  description = "returns a string"
  value       = avi_upgradestatusinfo.this.version
}

output "this" {
  value = avi_upgradestatusinfo.this
}
```

[top](#index)