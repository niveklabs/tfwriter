# docker_container

[back](../docker.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    docker = ">= 2.7.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "docker_container" {
  source = "./modules/docker/r/docker_container"

  # attach - (optional) is a type of bool
  attach = null
  # command - (optional) is a type of list of string
  command = []
  # cpu_set - (optional) is a type of string
  cpu_set = null
  # cpu_shares - (optional) is a type of number
  cpu_shares = null
  # destroy_grace_seconds - (optional) is a type of number
  destroy_grace_seconds = null
  # dns - (optional) is a type of set of string
  dns = []
  # dns_opts - (optional) is a type of set of string
  dns_opts = []
  # dns_search - (optional) is a type of set of string
  dns_search = []
  # domainname - (optional) is a type of string
  domainname = null
  # entrypoint - (optional) is a type of list of string
  entrypoint = []
  # env - (optional) is a type of set of string
  env = []
  # group_add - (optional) is a type of set of string
  group_add = []
  # hostname - (optional) is a type of string
  hostname = null
  # image - (required) is a type of string
  image = null
  # ipc_mode - (optional) is a type of string
  ipc_mode = null
  # links - (optional) is a type of set of string
  links = []
  # log_driver - (optional) is a type of string
  log_driver = null
  # log_opts - (optional) is a type of map of string
  log_opts = {}
  # logs - (optional) is a type of bool
  logs = null
  # max_retry_count - (optional) is a type of number
  max_retry_count = null
  # memory - (optional) is a type of number
  memory = null
  # memory_swap - (optional) is a type of number
  memory_swap = null
  # must_run - (optional) is a type of bool
  must_run = null
  # name - (required) is a type of string
  name = null
  # network_alias - (optional) is a type of set of string
  network_alias = []
  # network_mode - (optional) is a type of string
  network_mode = null
  # networks - (optional) is a type of set of string
  networks = []
  # pid_mode - (optional) is a type of string
  pid_mode = null
  # privileged - (optional) is a type of bool
  privileged = null
  # publish_all_ports - (optional) is a type of bool
  publish_all_ports = null
  # read_only - (optional) is a type of bool
  read_only = null
  # restart - (optional) is a type of string
  restart = null
  # rm - (optional) is a type of bool
  rm = null
  # shm_size - (optional) is a type of number
  shm_size = null
  # start - (optional) is a type of bool
  start = null
  # sysctls - (optional) is a type of map of string
  sysctls = {}
  # tmpfs - (optional) is a type of map of string
  tmpfs = {}
  # user - (optional) is a type of string
  user = null
  # userns_mode - (optional) is a type of string
  userns_mode = null
  # working_dir - (optional) is a type of string
  working_dir = null

  capabilities = [{
    add  = []
    drop = []
  }]

  devices = [{
    container_path = null
    host_path      = null
    permissions    = null
  }]

  healthcheck = [{
    interval     = null
    retries      = null
    start_period = null
    test         = []
    timeout      = null
  }]

  host = [{
    host = null
    ip   = null
  }]

  labels = [{
    label = null
    value = null
  }]

  mounts = [{
    bind_options = [{
      propagation = null
    }]
    read_only = null
    source    = null
    target    = null
    tmpfs_options = [{
      mode       = null
      size_bytes = null
    }]
    type = null
    volume_options = [{
      driver_name    = null
      driver_options = {}
      labels = [{
        label = null
        value = null
      }]
      no_copy = null
    }]
  }]

  networks_advanced = [{
    aliases      = []
    ipv4_address = null
    ipv6_address = null
    name         = null
  }]

  ports = [{
    external = null
    internal = null
    ip       = null
    protocol = null
  }]

  ulimit = [{
    hard = null
    name = null
    soft = null
  }]

  upload = [{
    content        = null
    content_base64 = null
    executable     = null
    file           = null
    source         = null
    source_hash    = null
  }]

  volumes = [{
    container_path = null
    from_container = null
    host_path      = null
    read_only      = null
    volume_name    = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "attach" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "command" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "cpu_set" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cpu_shares" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "destroy_grace_seconds" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dns" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "dns_opts" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "dns_search" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "domainname" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "entrypoint" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "env" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "group_add" {
  description = "(optional) - Additional groups for the container user"
  type        = set(string)
  default     = null
}

variable "hostname" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "image" {
  description = "(required)"
  type        = string
}

variable "ipc_mode" {
  description = "(optional) - IPC sharing mode for the container"
  type        = string
  default     = null
}

variable "links" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "log_driver" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "log_opts" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "logs" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "max_retry_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "memory" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "memory_swap" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "must_run" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "network_alias" {
  description = "(optional) - Set an alias for the container in all specified networks"
  type        = set(string)
  default     = null
}

variable "network_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "networks" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "pid_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "privileged" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "publish_all_ports" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "read_only" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "restart" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rm" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "shm_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "start" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "sysctls" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "tmpfs" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "user" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "userns_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "working_dir" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "capabilities" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      add  = set(string)
      drop = set(string)
    }
  ))
  default = []
}

variable "devices" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      container_path = string
      host_path      = string
      permissions    = string
    }
  ))
  default = []
}

variable "healthcheck" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      interval     = string
      retries      = number
      start_period = string
      test         = list(string)
      timeout      = string
    }
  ))
  default = []
}

variable "host" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      host = string
      ip   = string
    }
  ))
  default = []
}

variable "labels" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      label = string
      value = string
    }
  ))
  default = []
}

variable "mounts" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      bind_options = list(object(
        {
          propagation = string
        }
      ))
      read_only = bool
      source    = string
      target    = string
      tmpfs_options = list(object(
        {
          mode       = number
          size_bytes = number
        }
      ))
      type = string
      volume_options = list(object(
        {
          driver_name    = string
          driver_options = map(string)
          labels = set(object(
            {
              label = string
              value = string
            }
          ))
          no_copy = bool
        }
      ))
    }
  ))
  default = []
}

variable "networks_advanced" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      aliases      = set(string)
      ipv4_address = string
      ipv6_address = string
      name         = string
    }
  ))
  default = []
}

variable "ports" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      external = number
      internal = number
      ip       = string
      protocol = string
    }
  ))
  default = []
}

variable "ulimit" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      hard = number
      name = string
      soft = number
    }
  ))
  default = []
}

variable "upload" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      content        = string
      content_base64 = string
      executable     = bool
      file           = string
      source         = string
      source_hash    = string
    }
  ))
  default = []
}

variable "volumes" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      container_path = string
      from_container = string
      host_path      = string
      read_only      = bool
      volume_name    = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "docker_container" "this" {
  attach                = var.attach
  command               = var.command
  cpu_set               = var.cpu_set
  cpu_shares            = var.cpu_shares
  destroy_grace_seconds = var.destroy_grace_seconds
  dns                   = var.dns
  dns_opts              = var.dns_opts
  dns_search            = var.dns_search
  domainname            = var.domainname
  entrypoint            = var.entrypoint
  env                   = var.env
  group_add             = var.group_add
  hostname              = var.hostname
  image                 = var.image
  ipc_mode              = var.ipc_mode
  links                 = var.links
  log_driver            = var.log_driver
  log_opts              = var.log_opts
  logs                  = var.logs
  max_retry_count       = var.max_retry_count
  memory                = var.memory
  memory_swap           = var.memory_swap
  must_run              = var.must_run
  name                  = var.name
  network_alias         = var.network_alias
  network_mode          = var.network_mode
  networks              = var.networks
  pid_mode              = var.pid_mode
  privileged            = var.privileged
  publish_all_ports     = var.publish_all_ports
  read_only             = var.read_only
  restart               = var.restart
  rm                    = var.rm
  shm_size              = var.shm_size
  start                 = var.start
  sysctls               = var.sysctls
  tmpfs                 = var.tmpfs
  user                  = var.user
  userns_mode           = var.userns_mode
  working_dir           = var.working_dir

  dynamic "capabilities" {
    for_each = var.capabilities
    content {
      add  = capabilities.value["add"]
      drop = capabilities.value["drop"]
    }
  }

  dynamic "devices" {
    for_each = var.devices
    content {
      container_path = devices.value["container_path"]
      host_path      = devices.value["host_path"]
      permissions    = devices.value["permissions"]
    }
  }

  dynamic "healthcheck" {
    for_each = var.healthcheck
    content {
      interval     = healthcheck.value["interval"]
      retries      = healthcheck.value["retries"]
      start_period = healthcheck.value["start_period"]
      test         = healthcheck.value["test"]
      timeout      = healthcheck.value["timeout"]
    }
  }

  dynamic "host" {
    for_each = var.host
    content {
      host = host.value["host"]
      ip   = host.value["ip"]
    }
  }

  dynamic "labels" {
    for_each = var.labels
    content {
      label = labels.value["label"]
      value = labels.value["value"]
    }
  }

  dynamic "mounts" {
    for_each = var.mounts
    content {
      read_only = mounts.value["read_only"]
      source    = mounts.value["source"]
      target    = mounts.value["target"]
      type      = mounts.value["type"]

      dynamic "bind_options" {
        for_each = mounts.value.bind_options
        content {
          propagation = bind_options.value["propagation"]
        }
      }

      dynamic "tmpfs_options" {
        for_each = mounts.value.tmpfs_options
        content {
          mode       = tmpfs_options.value["mode"]
          size_bytes = tmpfs_options.value["size_bytes"]
        }
      }

      dynamic "volume_options" {
        for_each = mounts.value.volume_options
        content {
          driver_name    = volume_options.value["driver_name"]
          driver_options = volume_options.value["driver_options"]
          no_copy        = volume_options.value["no_copy"]

          dynamic "labels" {
            for_each = volume_options.value.labels
            content {
              label = labels.value["label"]
              value = labels.value["value"]
            }
          }

        }
      }

    }
  }

  dynamic "networks_advanced" {
    for_each = var.networks_advanced
    content {
      aliases      = networks_advanced.value["aliases"]
      ipv4_address = networks_advanced.value["ipv4_address"]
      ipv6_address = networks_advanced.value["ipv6_address"]
      name         = networks_advanced.value["name"]
    }
  }

  dynamic "ports" {
    for_each = var.ports
    content {
      external = ports.value["external"]
      internal = ports.value["internal"]
      ip       = ports.value["ip"]
      protocol = ports.value["protocol"]
    }
  }

  dynamic "ulimit" {
    for_each = var.ulimit
    content {
      hard = ulimit.value["hard"]
      name = ulimit.value["name"]
      soft = ulimit.value["soft"]
    }
  }

  dynamic "upload" {
    for_each = var.upload
    content {
      content        = upload.value["content"]
      content_base64 = upload.value["content_base64"]
      executable     = upload.value["executable"]
      file           = upload.value["file"]
      source         = upload.value["source"]
      source_hash    = upload.value["source_hash"]
    }
  }

  dynamic "volumes" {
    for_each = var.volumes
    content {
      container_path = volumes.value["container_path"]
      from_container = volumes.value["from_container"]
      host_path      = volumes.value["host_path"]
      read_only      = volumes.value["read_only"]
      volume_name    = volumes.value["volume_name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "bridge" {
  description = "returns a string"
  value       = docker_container.this.bridge
}

output "command" {
  description = "returns a list of string"
  value       = docker_container.this.command
}

output "container_logs" {
  description = "returns a string"
  value       = docker_container.this.container_logs
}

output "dns" {
  description = "returns a set of string"
  value       = docker_container.this.dns
}

output "dns_opts" {
  description = "returns a set of string"
  value       = docker_container.this.dns_opts
}

output "entrypoint" {
  description = "returns a list of string"
  value       = docker_container.this.entrypoint
}

output "exit_code" {
  description = "returns a number"
  value       = docker_container.this.exit_code
}

output "gateway" {
  description = "returns a string"
  value       = docker_container.this.gateway
}

output "hostname" {
  description = "returns a string"
  value       = docker_container.this.hostname
}

output "id" {
  description = "returns a string"
  value       = docker_container.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = docker_container.this.ip_address
}

output "ip_prefix_length" {
  description = "returns a number"
  value       = docker_container.this.ip_prefix_length
}

output "ipc_mode" {
  description = "returns a string"
  value       = docker_container.this.ipc_mode
}

output "log_driver" {
  description = "returns a string"
  value       = docker_container.this.log_driver
}

output "log_opts" {
  description = "returns a map of string"
  value       = docker_container.this.log_opts
}

output "network_data" {
  description = "returns a list of object"
  value       = docker_container.this.network_data
}

output "shm_size" {
  description = "returns a number"
  value       = docker_container.this.shm_size
}

output "user" {
  description = "returns a string"
  value       = docker_container.this.user
}

output "working_dir" {
  description = "returns a string"
  value       = docker_container.this.working_dir
}

output "this" {
  value = docker_container.this
}
```

[top](#index)