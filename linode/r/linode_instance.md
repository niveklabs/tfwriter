# linode_instance

[back](../linode.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    linode = ">= 1.16.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "linode_instance" {
  source = "./modules/linode/r/linode_instance"

  # authorized_keys - (optional) is a type of list of string
  authorized_keys = []
  # authorized_users - (optional) is a type of list of string
  authorized_users = []
  # backup_id - (optional) is a type of number
  backup_id = null
  # backups_enabled - (optional) is a type of bool
  backups_enabled = null
  # boot_config_label - (optional) is a type of string
  boot_config_label = null
  # group - (optional) is a type of string
  group = null
  # image - (optional) is a type of string
  image = null
  # label - (optional) is a type of string
  label = null
  # private_ip - (optional) is a type of bool
  private_ip = null
  # region - (required) is a type of string
  region = null
  # root_pass - (optional) is a type of string
  root_pass = null
  # stackscript_data - (optional) is a type of map of string
  stackscript_data = {}
  # stackscript_id - (optional) is a type of number
  stackscript_id = null
  # swap_size - (optional) is a type of number
  swap_size = null
  # tags - (optional) is a type of set of string
  tags = []
  # type - (optional) is a type of string
  type = null
  # watchdog_enabled - (optional) is a type of bool
  watchdog_enabled = null

  alerts = [{
    cpu            = null
    io             = null
    network_in     = null
    network_out    = null
    transfer_quota = null
  }]

  config = [{
    comments = null
    devices = [{
      sda = [{
        disk_id    = null
        disk_label = null
        volume_id  = null
      }]
      sdb = [{
        disk_id    = null
        disk_label = null
        volume_id  = null
      }]
      sdc = [{
        disk_id    = null
        disk_label = null
        volume_id  = null
      }]
      sdd = [{
        disk_id    = null
        disk_label = null
        volume_id  = null
      }]
      sde = [{
        disk_id    = null
        disk_label = null
        volume_id  = null
      }]
      sdf = [{
        disk_id    = null
        disk_label = null
        volume_id  = null
      }]
      sdg = [{
        disk_id    = null
        disk_label = null
        volume_id  = null
      }]
      sdh = [{
        disk_id    = null
        disk_label = null
        volume_id  = null
      }]
    }]
    helpers = [{
      devtmpfs_automount = null
      distro             = null
      modules_dep        = null
      network            = null
      updatedb_disabled  = null
    }]
    kernel       = null
    label        = null
    memory_limit = null
    root_device  = null
    run_level    = null
    virt_mode    = null
  }]

  disk = [{
    authorized_keys  = []
    authorized_users = []
    filesystem       = null
    id               = null
    image            = null
    label            = null
    read_only        = null
    root_pass        = null
    size             = null
    stackscript_data = {}
    stackscript_id   = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "authorized_keys" {
  description = "(optional) - A list of SSH public keys to deploy for the root user on the newly created Linode. Only accepted if 'image' is provided."
  type        = list(string)
  default     = null
}

variable "authorized_users" {
  description = "(optional) - A list of Linode usernames. If the usernames have associated SSH keys, the keys will be appended to the `root` user's `~/.ssh/authorized_keys` file automatically. Only accepted if 'image' is provided."
  type        = list(string)
  default     = null
}

variable "backup_id" {
  description = "(optional) - A Backup ID from another Linode's available backups. Your User must have read_write access to that Linode, the Backup must have a status of successful, and the Linode must be deployed to the same region as the Backup. See /linode/instances/{linodeId}/backups for a Linode's available backups. This field and the image field are mutually exclusive."
  type        = number
  default     = null
}

variable "backups_enabled" {
  description = "(optional) - If this field is set to true, the created Linode will automatically be enrolled in the Linode Backup service. This will incur an additional charge. The cost for the Backup service is dependent on the Type of Linode deployed."
  type        = bool
  default     = null
}

variable "boot_config_label" {
  description = "(optional) - The Label of the Instance Config that should be used to boot the Linode instance."
  type        = string
  default     = null
}

variable "group" {
  description = "(optional) - The display group of the Linode instance."
  type        = string
  default     = null
}

variable "image" {
  description = "(optional) - An Image ID to deploy the Disk from. Official Linode Images start with linode/, while your Images start with private/. See /images for more information on the Images available for you to use."
  type        = string
  default     = null
}

variable "label" {
  description = "(optional) - The Linode's label is for display purposes only. If no label is provided for a Linode, a default will be assigned"
  type        = string
  default     = null
}

variable "private_ip" {
  description = "(optional) - If true, the created Linode will have private networking enabled, allowing use of the 192.168.128.0/17 network within the Linode's region."
  type        = bool
  default     = null
}

variable "region" {
  description = "(required) - This is the location where the Linode was deployed. This cannot be changed without opening a support ticket."
  type        = string
}

variable "root_pass" {
  description = "(optional) - The password that will be initialially assigned to the 'root' user account."
  type        = string
  default     = null
}

variable "stackscript_data" {
  description = "(optional) - An object containing responses to any User Defined Fields present in the StackScript being deployed to this Linode. Only accepted if 'stackscript_id' is given. The required values depend on the StackScript being deployed."
  type        = map(string)
  default     = null
}

variable "stackscript_id" {
  description = "(optional) - The StackScript to deploy to the newly created Linode. If provided, 'image' must also be provided, and must be an Image that is compatible with this StackScript."
  type        = number
  default     = null
}

variable "swap_size" {
  description = "(optional) - When deploying from an Image, this field is optional with a Linode API default of 512mb, otherwise it is ignored. This is used to set the swap disk size for the newly-created Linode."
  type        = number
  default     = null
}

variable "tags" {
  description = "(optional) - An array of tags applied to this object. Tags are for organizational purposes only."
  type        = set(string)
  default     = null
}

variable "type" {
  description = "(optional) - The type of instance to be deployed, determining the price and size."
  type        = string
  default     = null
}

variable "watchdog_enabled" {
  description = "(optional) - The watchdog, named Lassie, is a Shutdown Watchdog that monitors your Linode and will reboot it if it powers off unexpectedly. It works by issuing a boot job when your Linode powers off without a shutdown job being responsible. To prevent a loop, Lassie will give up if there have been more than 5 boot jobs issued within 15 minutes."
  type        = bool
  default     = null
}

variable "alerts" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cpu            = number
      io             = number
      network_in     = number
      network_out    = number
      transfer_quota = number
    }
  ))
  default = []
}

variable "config" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      comments = string
      devices = list(object(
        {
          sda = list(object(
            {
              disk_id    = number
              disk_label = string
              volume_id  = number
            }
          ))
          sdb = list(object(
            {
              disk_id    = number
              disk_label = string
              volume_id  = number
            }
          ))
          sdc = list(object(
            {
              disk_id    = number
              disk_label = string
              volume_id  = number
            }
          ))
          sdd = list(object(
            {
              disk_id    = number
              disk_label = string
              volume_id  = number
            }
          ))
          sde = list(object(
            {
              disk_id    = number
              disk_label = string
              volume_id  = number
            }
          ))
          sdf = list(object(
            {
              disk_id    = number
              disk_label = string
              volume_id  = number
            }
          ))
          sdg = list(object(
            {
              disk_id    = number
              disk_label = string
              volume_id  = number
            }
          ))
          sdh = list(object(
            {
              disk_id    = number
              disk_label = string
              volume_id  = number
            }
          ))
        }
      ))
      helpers = list(object(
        {
          devtmpfs_automount = bool
          distro             = bool
          modules_dep        = bool
          network            = bool
          updatedb_disabled  = bool
        }
      ))
      kernel       = string
      label        = string
      memory_limit = number
      root_device  = string
      run_level    = string
      virt_mode    = string
    }
  ))
  default = []
}

variable "disk" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      authorized_keys  = list(string)
      authorized_users = list(string)
      filesystem       = string
      id               = number
      image            = string
      label            = string
      read_only        = bool
      root_pass        = string
      size             = number
      stackscript_data = map(string)
      stackscript_id   = number
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "linode_instance" "this" {
  authorized_keys   = var.authorized_keys
  authorized_users  = var.authorized_users
  backup_id         = var.backup_id
  backups_enabled   = var.backups_enabled
  boot_config_label = var.boot_config_label
  group             = var.group
  image             = var.image
  label             = var.label
  private_ip        = var.private_ip
  region            = var.region
  root_pass         = var.root_pass
  stackscript_data  = var.stackscript_data
  stackscript_id    = var.stackscript_id
  swap_size         = var.swap_size
  tags              = var.tags
  type              = var.type
  watchdog_enabled  = var.watchdog_enabled

  dynamic "alerts" {
    for_each = var.alerts
    content {
      cpu            = alerts.value["cpu"]
      io             = alerts.value["io"]
      network_in     = alerts.value["network_in"]
      network_out    = alerts.value["network_out"]
      transfer_quota = alerts.value["transfer_quota"]
    }
  }

  dynamic "config" {
    for_each = var.config
    content {
      comments     = config.value["comments"]
      kernel       = config.value["kernel"]
      label        = config.value["label"]
      memory_limit = config.value["memory_limit"]
      root_device  = config.value["root_device"]
      run_level    = config.value["run_level"]
      virt_mode    = config.value["virt_mode"]

      dynamic "devices" {
        for_each = config.value.devices
        content {

          dynamic "sda" {
            for_each = devices.value.sda
            content {
              disk_id    = sda.value["disk_id"]
              disk_label = sda.value["disk_label"]
              volume_id  = sda.value["volume_id"]
            }
          }

          dynamic "sdb" {
            for_each = devices.value.sdb
            content {
              disk_id    = sdb.value["disk_id"]
              disk_label = sdb.value["disk_label"]
              volume_id  = sdb.value["volume_id"]
            }
          }

          dynamic "sdc" {
            for_each = devices.value.sdc
            content {
              disk_id    = sdc.value["disk_id"]
              disk_label = sdc.value["disk_label"]
              volume_id  = sdc.value["volume_id"]
            }
          }

          dynamic "sdd" {
            for_each = devices.value.sdd
            content {
              disk_id    = sdd.value["disk_id"]
              disk_label = sdd.value["disk_label"]
              volume_id  = sdd.value["volume_id"]
            }
          }

          dynamic "sde" {
            for_each = devices.value.sde
            content {
              disk_id    = sde.value["disk_id"]
              disk_label = sde.value["disk_label"]
              volume_id  = sde.value["volume_id"]
            }
          }

          dynamic "sdf" {
            for_each = devices.value.sdf
            content {
              disk_id    = sdf.value["disk_id"]
              disk_label = sdf.value["disk_label"]
              volume_id  = sdf.value["volume_id"]
            }
          }

          dynamic "sdg" {
            for_each = devices.value.sdg
            content {
              disk_id    = sdg.value["disk_id"]
              disk_label = sdg.value["disk_label"]
              volume_id  = sdg.value["volume_id"]
            }
          }

          dynamic "sdh" {
            for_each = devices.value.sdh
            content {
              disk_id    = sdh.value["disk_id"]
              disk_label = sdh.value["disk_label"]
              volume_id  = sdh.value["volume_id"]
            }
          }

        }
      }

      dynamic "helpers" {
        for_each = config.value.helpers
        content {
          devtmpfs_automount = helpers.value["devtmpfs_automount"]
          distro             = helpers.value["distro"]
          modules_dep        = helpers.value["modules_dep"]
          network            = helpers.value["network"]
          updatedb_disabled  = helpers.value["updatedb_disabled"]
        }
      }

    }
  }

  dynamic "disk" {
    for_each = var.disk
    content {
      authorized_keys  = disk.value["authorized_keys"]
      authorized_users = disk.value["authorized_users"]
      filesystem       = disk.value["filesystem"]
      image            = disk.value["image"]
      label            = disk.value["label"]
      read_only        = disk.value["read_only"]
      root_pass        = disk.value["root_pass"]
      size             = disk.value["size"]
      stackscript_data = disk.value["stackscript_data"]
      stackscript_id   = disk.value["stackscript_id"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "backups" {
  description = "returns a list of object"
  value       = linode_instance.this.backups
}

output "backups_enabled" {
  description = "returns a bool"
  value       = linode_instance.this.backups_enabled
}

output "boot_config_label" {
  description = "returns a string"
  value       = linode_instance.this.boot_config_label
}

output "id" {
  description = "returns a string"
  value       = linode_instance.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = linode_instance.this.ip_address
}

output "ipv4" {
  description = "returns a set of string"
  value       = linode_instance.this.ipv4
}

output "ipv6" {
  description = "returns a string"
  value       = linode_instance.this.ipv6
}

output "label" {
  description = "returns a string"
  value       = linode_instance.this.label
}

output "private_ip_address" {
  description = "returns a string"
  value       = linode_instance.this.private_ip_address
}

output "specs" {
  description = "returns a list of object"
  value       = linode_instance.this.specs
}

output "status" {
  description = "returns a string"
  value       = linode_instance.this.status
}

output "swap_size" {
  description = "returns a number"
  value       = linode_instance.this.swap_size
}

output "this" {
  value = linode_instance.this
}
```

[top](#index)