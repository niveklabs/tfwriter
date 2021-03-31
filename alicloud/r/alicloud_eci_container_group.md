# alicloud_eci_container_group

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_eci_container_group" {
  source = "./modules/alicloud/r/alicloud_eci_container_group"

  # container_group_name - (required) is a type of string
  container_group_name = null
  # cpu - (optional) is a type of number
  cpu = null
  # instance_type - (optional) is a type of string
  instance_type = null
  # memory - (optional) is a type of number
  memory = null
  # ram_role_name - (optional) is a type of string
  ram_role_name = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # restart_policy - (optional) is a type of string
  restart_policy = null
  # security_group_id - (required) is a type of string
  security_group_id = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vswitch_id - (required) is a type of string
  vswitch_id = null
  # zone_id - (optional) is a type of string
  zone_id = null

  containers = [{
    args     = []
    commands = []
    cpu      = null
    environment_vars = [{
      key   = null
      value = null
    }]
    gpu               = null
    image             = null
    image_pull_policy = null
    memory            = null
    name              = null
    ports = [{
      port     = null
      protocol = null
    }]
    ready         = null
    restart_count = null
    volume_mounts = [{
      mount_path = null
      name       = null
      read_only  = null
    }]
    working_dir = null
  }]

  dns_config = [{
    name_servers = []
    options = [{
      name  = null
      value = null
    }]
    searches = []
  }]

  eci_security_context = [{
    sysctls = [{
      name  = null
      value = null
    }]
  }]

  host_aliases = [{
    hostnames = []
    ip        = null
  }]

  init_containers = [{
    args     = []
    commands = []
    cpu      = null
    environment_vars = [{
      key   = null
      value = null
    }]
    gpu               = null
    image             = null
    image_pull_policy = null
    memory            = null
    name              = null
    ports = [{
      port     = null
      protocol = null
    }]
    ready         = null
    restart_count = null
    volume_mounts = [{
      mount_path = null
      name       = null
      read_only  = null
    }]
    working_dir = null
  }]

  timeouts = [{
    create = null
    update = null
  }]

  volumes = [{
    config_file_volume_config_file_to_paths = [{
      content = null
      path    = null
    }]
    disk_volume_disk_id  = null
    disk_volume_fs_type  = null
    flex_volume_driver   = null
    flex_volume_fs_type  = null
    flex_volume_options  = null
    name                 = null
    nfs_volume_path      = null
    nfs_volume_read_only = null
    nfs_volume_server    = null
    type                 = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "container_group_name" {
  description = "(required)"
  type        = string
}

variable "cpu" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "instance_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "memory" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ram_role_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "restart_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_group_id" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "vswitch_id" {
  description = "(required)"
  type        = string
}

variable "zone_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "containers" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      args     = list(string)
      commands = list(string)
      cpu      = number
      environment_vars = list(object(
        {
          key   = string
          value = string
        }
      ))
      gpu               = number
      image             = string
      image_pull_policy = string
      memory            = number
      name              = string
      ports = list(object(
        {
          port     = number
          protocol = string
        }
      ))
      ready         = bool
      restart_count = number
      volume_mounts = list(object(
        {
          mount_path = string
          name       = string
          read_only  = bool
        }
      ))
      working_dir = string
    }
  ))
}

variable "dns_config" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      name_servers = list(string)
      options = list(object(
        {
          name  = string
          value = string
        }
      ))
      searches = list(string)
    }
  ))
  default = []
}

variable "eci_security_context" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      sysctls = list(object(
        {
          name  = string
          value = string
        }
      ))
    }
  ))
  default = []
}

variable "host_aliases" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      hostnames = list(string)
      ip        = string
    }
  ))
  default = []
}

variable "init_containers" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      args     = list(string)
      commands = list(string)
      cpu      = number
      environment_vars = list(object(
        {
          key   = string
          value = string
        }
      ))
      gpu               = number
      image             = string
      image_pull_policy = string
      memory            = number
      name              = string
      ports = list(object(
        {
          port     = number
          protocol = string
        }
      ))
      ready         = bool
      restart_count = number
      volume_mounts = list(object(
        {
          mount_path = string
          name       = string
          read_only  = bool
        }
      ))
      working_dir = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      update = string
    }
  ))
  default = []
}

variable "volumes" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      config_file_volume_config_file_to_paths = list(object(
        {
          content = string
          path    = string
        }
      ))
      disk_volume_disk_id  = string
      disk_volume_fs_type  = string
      flex_volume_driver   = string
      flex_volume_fs_type  = string
      flex_volume_options  = string
      name                 = string
      nfs_volume_path      = string
      nfs_volume_read_only = bool
      nfs_volume_server    = string
      type                 = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_eci_container_group" "this" {
  container_group_name = var.container_group_name
  cpu                  = var.cpu
  instance_type        = var.instance_type
  memory               = var.memory
  ram_role_name        = var.ram_role_name
  resource_group_id    = var.resource_group_id
  restart_policy       = var.restart_policy
  security_group_id    = var.security_group_id
  tags                 = var.tags
  vswitch_id           = var.vswitch_id
  zone_id              = var.zone_id

  dynamic "containers" {
    for_each = var.containers
    content {
      args              = containers.value["args"]
      commands          = containers.value["commands"]
      cpu               = containers.value["cpu"]
      gpu               = containers.value["gpu"]
      image             = containers.value["image"]
      image_pull_policy = containers.value["image_pull_policy"]
      memory            = containers.value["memory"]
      name              = containers.value["name"]
      working_dir       = containers.value["working_dir"]

      dynamic "environment_vars" {
        for_each = containers.value.environment_vars
        content {
          key   = environment_vars.value["key"]
          value = environment_vars.value["value"]
        }
      }

      dynamic "ports" {
        for_each = containers.value.ports
        content {
          port     = ports.value["port"]
          protocol = ports.value["protocol"]
        }
      }

      dynamic "volume_mounts" {
        for_each = containers.value.volume_mounts
        content {
          mount_path = volume_mounts.value["mount_path"]
          name       = volume_mounts.value["name"]
          read_only  = volume_mounts.value["read_only"]
        }
      }

    }
  }

  dynamic "dns_config" {
    for_each = var.dns_config
    content {
      name_servers = dns_config.value["name_servers"]
      searches     = dns_config.value["searches"]

      dynamic "options" {
        for_each = dns_config.value.options
        content {
          name  = options.value["name"]
          value = options.value["value"]
        }
      }

    }
  }

  dynamic "eci_security_context" {
    for_each = var.eci_security_context
    content {

      dynamic "sysctls" {
        for_each = eci_security_context.value.sysctls
        content {
          name  = sysctls.value["name"]
          value = sysctls.value["value"]
        }
      }

    }
  }

  dynamic "host_aliases" {
    for_each = var.host_aliases
    content {
      hostnames = host_aliases.value["hostnames"]
      ip        = host_aliases.value["ip"]
    }
  }

  dynamic "init_containers" {
    for_each = var.init_containers
    content {
      args              = init_containers.value["args"]
      commands          = init_containers.value["commands"]
      cpu               = init_containers.value["cpu"]
      gpu               = init_containers.value["gpu"]
      image             = init_containers.value["image"]
      image_pull_policy = init_containers.value["image_pull_policy"]
      memory            = init_containers.value["memory"]
      name              = init_containers.value["name"]
      working_dir       = init_containers.value["working_dir"]

      dynamic "environment_vars" {
        for_each = init_containers.value.environment_vars
        content {
          key   = environment_vars.value["key"]
          value = environment_vars.value["value"]
        }
      }

      dynamic "ports" {
        for_each = init_containers.value.ports
        content {
          port     = ports.value["port"]
          protocol = ports.value["protocol"]
        }
      }

      dynamic "volume_mounts" {
        for_each = init_containers.value.volume_mounts
        content {
          mount_path = volume_mounts.value["mount_path"]
          name       = volume_mounts.value["name"]
          read_only  = volume_mounts.value["read_only"]
        }
      }

    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      update = timeouts.value["update"]
    }
  }

  dynamic "volumes" {
    for_each = var.volumes
    content {
      disk_volume_disk_id  = volumes.value["disk_volume_disk_id"]
      disk_volume_fs_type  = volumes.value["disk_volume_fs_type"]
      flex_volume_driver   = volumes.value["flex_volume_driver"]
      flex_volume_fs_type  = volumes.value["flex_volume_fs_type"]
      flex_volume_options  = volumes.value["flex_volume_options"]
      name                 = volumes.value["name"]
      nfs_volume_path      = volumes.value["nfs_volume_path"]
      nfs_volume_read_only = volumes.value["nfs_volume_read_only"]
      nfs_volume_server    = volumes.value["nfs_volume_server"]
      type                 = volumes.value["type"]

      dynamic "config_file_volume_config_file_to_paths" {
        for_each = volumes.value.config_file_volume_config_file_to_paths
        content {
          content = config_file_volume_config_file_to_paths.value["content"]
          path    = config_file_volume_config_file_to_paths.value["path"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_eci_container_group.this.id
}

output "resource_group_id" {
  description = "returns a string"
  value       = alicloud_eci_container_group.this.resource_group_id
}

output "status" {
  description = "returns a string"
  value       = alicloud_eci_container_group.this.status
}

output "zone_id" {
  description = "returns a string"
  value       = alicloud_eci_container_group.this.zone_id
}

output "this" {
  value = alicloud_eci_container_group.this
}
```

[top](#index)