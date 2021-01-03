# ovh_dedicated_server_install_task

[back](../ovh.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ovh = ">= 0.10.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ovh_dedicated_server_install_task" {
  source = "./modules/ovh/r/ovh_dedicated_server_install_task"

  # bootid_on_destroy - (optional) is a type of number
  bootid_on_destroy = null
  # partition_scheme_name - (optional) is a type of string
  partition_scheme_name = null
  # service_name - (required) is a type of string
  service_name = null
  # template_name - (required) is a type of string
  template_name = null

  details = [{
    change_log                      = null
    custom_hostname                 = null
    disk_group_id                   = null
    install_rtm                     = null
    install_sql_server              = null
    language                        = null
    no_raid                         = null
    post_installation_script_link   = null
    post_installation_script_return = null
    reset_hw_raid                   = null
    soft_raid_devices               = null
    ssh_key_name                    = null
    use_distrib_kernel              = null
    use_spla                        = null
  }]

  timeouts = [{
    create = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "bootid_on_destroy" {
  description = "(optional) - If set, reboot the server on the specified boot id during destroy phase"
  type        = number
  default     = null
}

variable "partition_scheme_name" {
  description = "(optional) - Partition scheme name."
  type        = string
  default     = null
}

variable "service_name" {
  description = "(required) - The internal name of your dedicated server."
  type        = string
}

variable "template_name" {
  description = "(required) - Template name"
  type        = string
}

variable "details" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      change_log                      = string
      custom_hostname                 = string
      disk_group_id                   = number
      install_rtm                     = bool
      install_sql_server              = bool
      language                        = string
      no_raid                         = bool
      post_installation_script_link   = string
      post_installation_script_return = string
      reset_hw_raid                   = bool
      soft_raid_devices               = number
      ssh_key_name                    = string
      use_distrib_kernel              = bool
      use_spla                        = bool
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "ovh_dedicated_server_install_task" "this" {
  bootid_on_destroy     = var.bootid_on_destroy
  partition_scheme_name = var.partition_scheme_name
  service_name          = var.service_name
  template_name         = var.template_name

  dynamic "details" {
    for_each = var.details
    content {
      change_log                      = details.value["change_log"]
      custom_hostname                 = details.value["custom_hostname"]
      disk_group_id                   = details.value["disk_group_id"]
      install_rtm                     = details.value["install_rtm"]
      install_sql_server              = details.value["install_sql_server"]
      language                        = details.value["language"]
      no_raid                         = details.value["no_raid"]
      post_installation_script_link   = details.value["post_installation_script_link"]
      post_installation_script_return = details.value["post_installation_script_return"]
      reset_hw_raid                   = details.value["reset_hw_raid"]
      soft_raid_devices               = details.value["soft_raid_devices"]
      ssh_key_name                    = details.value["ssh_key_name"]
      use_distrib_kernel              = details.value["use_distrib_kernel"]
      use_spla                        = details.value["use_spla"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "comment" {
  description = "returns a string"
  value       = ovh_dedicated_server_install_task.this.comment
}

output "done_date" {
  description = "returns a string"
  value       = ovh_dedicated_server_install_task.this.done_date
}

output "function" {
  description = "returns a string"
  value       = ovh_dedicated_server_install_task.this.function
}

output "id" {
  description = "returns a string"
  value       = ovh_dedicated_server_install_task.this.id
}

output "last_update" {
  description = "returns a string"
  value       = ovh_dedicated_server_install_task.this.last_update
}

output "start_date" {
  description = "returns a string"
  value       = ovh_dedicated_server_install_task.this.start_date
}

output "status" {
  description = "returns a string"
  value       = ovh_dedicated_server_install_task.this.status
}

output "this" {
  value = ovh_dedicated_server_install_task.this
}
```

[top](#index)