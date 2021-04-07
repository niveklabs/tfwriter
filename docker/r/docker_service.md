# docker_service

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
module "docker_service" {
  source = "./modules/docker/r/docker_service"

  # auth - (optional) is a type of map of string
  auth = {}
  # name - (required) is a type of string
  name = null

  converge_config = [{
    delay   = null
    timeout = null
  }]

  endpoint_spec = [{
    mode = null
    ports = [{
      name           = null
      protocol       = null
      publish_mode   = null
      published_port = null
      target_port    = null
    }]
  }]

  labels = [{
    label = null
    value = null
  }]

  mode = [{
    global = null
    replicated = [{
      replicas = null
    }]
  }]

  rollback_config = [{
    delay             = null
    failure_action    = null
    max_failure_ratio = null
    monitor           = null
    order             = null
    parallelism       = null
  }]

  task_spec = [{
    container_spec = [{
      args    = []
      command = []
      configs = [{
        config_id   = null
        config_name = null
        file_gid    = null
        file_mode   = null
        file_name   = null
        file_uid    = null
      }]
      dir = null
      dns_config = [{
        nameservers = []
        options     = []
        search      = []
      }]
      env    = {}
      groups = []
      healthcheck = [{
        interval     = null
        retries      = null
        start_period = null
        test         = []
        timeout      = null
      }]
      hostname = null
      hosts = [{
        host = null
        ip   = null
      }]
      image     = null
      isolation = null
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
      privileges = [{
        credential_spec = [{
          file     = null
          registry = null
        }]
        se_linux_context = [{
          disable = null
          level   = null
          role    = null
          type    = null
          user    = null
        }]
      }]
      read_only = null
      secrets = [{
        file_gid    = null
        file_mode   = null
        file_name   = null
        file_uid    = null
        secret_id   = null
        secret_name = null
      }]
      stop_grace_period = null
      stop_signal       = null
      user              = null
    }]
    force_update = null
    log_driver = [{
      name    = null
      options = {}
    }]
    networks = []
    placement = [{
      constraints = []
      platforms = [{
        architecture = null
        os           = null
      }]
      prefs = []
    }]
    resources = [{
      limits = [{
        generic_resources = [{
          discrete_resources_spec = []
          named_resources_spec    = []
        }]
        memory_bytes = null
        nano_cpus    = null
      }]
      reservation = [{
        generic_resources = [{
          discrete_resources_spec = []
          named_resources_spec    = []
        }]
        memory_bytes = null
        nano_cpus    = null
      }]
    }]
    restart_policy = {}
    runtime        = null
  }]

  update_config = [{
    delay             = null
    failure_action    = null
    max_failure_ratio = null
    monitor           = null
    order             = null
    parallelism       = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "auth" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - Name of the service"
  type        = string
}

variable "converge_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      delay   = string
      timeout = string
    }
  ))
  default = []
}

variable "endpoint_spec" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      mode = string
      ports = list(object(
        {
          name           = string
          protocol       = string
          publish_mode   = string
          published_port = number
          target_port    = number
        }
      ))
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

variable "mode" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      global = bool
      replicated = list(object(
        {
          replicas = number
        }
      ))
    }
  ))
  default = []
}

variable "rollback_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      delay             = string
      failure_action    = string
      max_failure_ratio = string
      monitor           = string
      order             = string
      parallelism       = number
    }
  ))
  default = []
}

variable "task_spec" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      container_spec = list(object(
        {
          args    = list(string)
          command = list(string)
          configs = set(object(
            {
              config_id   = string
              config_name = string
              file_gid    = string
              file_mode   = number
              file_name   = string
              file_uid    = string
            }
          ))
          dir = string
          dns_config = list(object(
            {
              nameservers = list(string)
              options     = list(string)
              search      = list(string)
            }
          ))
          env    = map(string)
          groups = list(string)
          healthcheck = list(object(
            {
              interval     = string
              retries      = number
              start_period = string
              test         = list(string)
              timeout      = string
            }
          ))
          hostname = string
          hosts = set(object(
            {
              host = string
              ip   = string
            }
          ))
          image     = string
          isolation = string
          labels = set(object(
            {
              label = string
              value = string
            }
          ))
          mounts = set(object(
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
          privileges = list(object(
            {
              credential_spec = list(object(
                {
                  file     = string
                  registry = string
                }
              ))
              se_linux_context = list(object(
                {
                  disable = bool
                  level   = string
                  role    = string
                  type    = string
                  user    = string
                }
              ))
            }
          ))
          read_only = bool
          secrets = set(object(
            {
              file_gid    = string
              file_mode   = number
              file_name   = string
              file_uid    = string
              secret_id   = string
              secret_name = string
            }
          ))
          stop_grace_period = string
          stop_signal       = string
          user              = string
        }
      ))
      force_update = number
      log_driver = list(object(
        {
          name    = string
          options = map(string)
        }
      ))
      networks = set(string)
      placement = list(object(
        {
          constraints = set(string)
          platforms = set(object(
            {
              architecture = string
              os           = string
            }
          ))
          prefs = set(string)
        }
      ))
      resources = list(object(
        {
          limits = list(object(
            {
              generic_resources = list(object(
                {
                  discrete_resources_spec = set(string)
                  named_resources_spec    = set(string)
                }
              ))
              memory_bytes = number
              nano_cpus    = number
            }
          ))
          reservation = list(object(
            {
              generic_resources = list(object(
                {
                  discrete_resources_spec = set(string)
                  named_resources_spec    = set(string)
                }
              ))
              memory_bytes = number
              nano_cpus    = number
            }
          ))
        }
      ))
      restart_policy = map(string)
      runtime        = string
    }
  ))
}

variable "update_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      delay             = string
      failure_action    = string
      max_failure_ratio = string
      monitor           = string
      order             = string
      parallelism       = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "docker_service" "this" {
  # auth - (optional) is a type of map of string
  auth = var.auth
  # name - (required) is a type of string
  name = var.name

  dynamic "converge_config" {
    for_each = var.converge_config
    content {
      # delay - (optional) is a type of string
      delay = converge_config.value["delay"]
      # timeout - (optional) is a type of string
      timeout = converge_config.value["timeout"]
    }
  }

  dynamic "endpoint_spec" {
    for_each = var.endpoint_spec
    content {
      # mode - (optional) is a type of string
      mode = endpoint_spec.value["mode"]

      dynamic "ports" {
        for_each = endpoint_spec.value.ports
        content {
          # name - (optional) is a type of string
          name = ports.value["name"]
          # protocol - (optional) is a type of string
          protocol = ports.value["protocol"]
          # publish_mode - (optional) is a type of string
          publish_mode = ports.value["publish_mode"]
          # published_port - (optional) is a type of number
          published_port = ports.value["published_port"]
          # target_port - (required) is a type of number
          target_port = ports.value["target_port"]
        }
      }

    }
  }

  dynamic "labels" {
    for_each = var.labels
    content {
      # label - (required) is a type of string
      label = labels.value["label"]
      # value - (required) is a type of string
      value = labels.value["value"]
    }
  }

  dynamic "mode" {
    for_each = var.mode
    content {
      # global - (optional) is a type of bool
      global = mode.value["global"]

      dynamic "replicated" {
        for_each = mode.value.replicated
        content {
          # replicas - (optional) is a type of number
          replicas = replicated.value["replicas"]
        }
      }

    }
  }

  dynamic "rollback_config" {
    for_each = var.rollback_config
    content {
      # delay - (optional) is a type of string
      delay = rollback_config.value["delay"]
      # failure_action - (optional) is a type of string
      failure_action = rollback_config.value["failure_action"]
      # max_failure_ratio - (optional) is a type of string
      max_failure_ratio = rollback_config.value["max_failure_ratio"]
      # monitor - (optional) is a type of string
      monitor = rollback_config.value["monitor"]
      # order - (optional) is a type of string
      order = rollback_config.value["order"]
      # parallelism - (optional) is a type of number
      parallelism = rollback_config.value["parallelism"]
    }
  }

  dynamic "task_spec" {
    for_each = var.task_spec
    content {
      # force_update - (optional) is a type of number
      force_update = task_spec.value["force_update"]
      # networks - (optional) is a type of set of string
      networks = task_spec.value["networks"]
      # restart_policy - (optional) is a type of map of string
      restart_policy = task_spec.value["restart_policy"]
      # runtime - (optional) is a type of string
      runtime = task_spec.value["runtime"]

      dynamic "container_spec" {
        for_each = task_spec.value.container_spec
        content {
          # args - (optional) is a type of list of string
          args = container_spec.value["args"]
          # command - (optional) is a type of list of string
          command = container_spec.value["command"]
          # dir - (optional) is a type of string
          dir = container_spec.value["dir"]
          # env - (optional) is a type of map of string
          env = container_spec.value["env"]
          # groups - (optional) is a type of list of string
          groups = container_spec.value["groups"]
          # hostname - (optional) is a type of string
          hostname = container_spec.value["hostname"]
          # image - (required) is a type of string
          image = container_spec.value["image"]
          # isolation - (optional) is a type of string
          isolation = container_spec.value["isolation"]
          # read_only - (optional) is a type of bool
          read_only = container_spec.value["read_only"]
          # stop_grace_period - (optional) is a type of string
          stop_grace_period = container_spec.value["stop_grace_period"]
          # stop_signal - (optional) is a type of string
          stop_signal = container_spec.value["stop_signal"]
          # user - (optional) is a type of string
          user = container_spec.value["user"]

          dynamic "configs" {
            for_each = container_spec.value.configs
            content {
              # config_id - (required) is a type of string
              config_id = configs.value["config_id"]
              # config_name - (optional) is a type of string
              config_name = configs.value["config_name"]
              # file_gid - (optional) is a type of string
              file_gid = configs.value["file_gid"]
              # file_mode - (optional) is a type of number
              file_mode = configs.value["file_mode"]
              # file_name - (required) is a type of string
              file_name = configs.value["file_name"]
              # file_uid - (optional) is a type of string
              file_uid = configs.value["file_uid"]
            }
          }

          dynamic "dns_config" {
            for_each = container_spec.value.dns_config
            content {
              # nameservers - (required) is a type of list of string
              nameservers = dns_config.value["nameservers"]
              # options - (optional) is a type of list of string
              options = dns_config.value["options"]
              # search - (optional) is a type of list of string
              search = dns_config.value["search"]
            }
          }

          dynamic "healthcheck" {
            for_each = container_spec.value.healthcheck
            content {
              # interval - (optional) is a type of string
              interval = healthcheck.value["interval"]
              # retries - (optional) is a type of number
              retries = healthcheck.value["retries"]
              # start_period - (optional) is a type of string
              start_period = healthcheck.value["start_period"]
              # test - (required) is a type of list of string
              test = healthcheck.value["test"]
              # timeout - (optional) is a type of string
              timeout = healthcheck.value["timeout"]
            }
          }

          dynamic "hosts" {
            for_each = container_spec.value.hosts
            content {
              # host - (required) is a type of string
              host = hosts.value["host"]
              # ip - (required) is a type of string
              ip = hosts.value["ip"]
            }
          }

          dynamic "labels" {
            for_each = container_spec.value.labels
            content {
              # label - (required) is a type of string
              label = labels.value["label"]
              # value - (required) is a type of string
              value = labels.value["value"]
            }
          }

          dynamic "mounts" {
            for_each = container_spec.value.mounts
            content {
              # read_only - (optional) is a type of bool
              read_only = mounts.value["read_only"]
              # source - (optional) is a type of string
              source = mounts.value["source"]
              # target - (required) is a type of string
              target = mounts.value["target"]
              # type - (required) is a type of string
              type = mounts.value["type"]

              dynamic "bind_options" {
                for_each = mounts.value.bind_options
                content {
                  # propagation - (optional) is a type of string
                  propagation = bind_options.value["propagation"]
                }
              }

              dynamic "tmpfs_options" {
                for_each = mounts.value.tmpfs_options
                content {
                  # mode - (optional) is a type of number
                  mode = tmpfs_options.value["mode"]
                  # size_bytes - (optional) is a type of number
                  size_bytes = tmpfs_options.value["size_bytes"]
                }
              }

              dynamic "volume_options" {
                for_each = mounts.value.volume_options
                content {
                  # driver_name - (optional) is a type of string
                  driver_name = volume_options.value["driver_name"]
                  # driver_options - (optional) is a type of map of string
                  driver_options = volume_options.value["driver_options"]
                  # no_copy - (optional) is a type of bool
                  no_copy = volume_options.value["no_copy"]

                  dynamic "labels" {
                    for_each = volume_options.value.labels
                    content {
                      # label - (required) is a type of string
                      label = labels.value["label"]
                      # value - (required) is a type of string
                      value = labels.value["value"]
                    }
                  }

                }
              }

            }
          }

          dynamic "privileges" {
            for_each = container_spec.value.privileges
            content {

              dynamic "credential_spec" {
                for_each = privileges.value.credential_spec
                content {
                  # file - (optional) is a type of string
                  file = credential_spec.value["file"]
                  # registry - (optional) is a type of string
                  registry = credential_spec.value["registry"]
                }
              }

              dynamic "se_linux_context" {
                for_each = privileges.value.se_linux_context
                content {
                  # disable - (optional) is a type of bool
                  disable = se_linux_context.value["disable"]
                  # level - (optional) is a type of string
                  level = se_linux_context.value["level"]
                  # role - (optional) is a type of string
                  role = se_linux_context.value["role"]
                  # type - (optional) is a type of string
                  type = se_linux_context.value["type"]
                  # user - (optional) is a type of string
                  user = se_linux_context.value["user"]
                }
              }

            }
          }

          dynamic "secrets" {
            for_each = container_spec.value.secrets
            content {
              # file_gid - (optional) is a type of string
              file_gid = secrets.value["file_gid"]
              # file_mode - (optional) is a type of number
              file_mode = secrets.value["file_mode"]
              # file_name - (required) is a type of string
              file_name = secrets.value["file_name"]
              # file_uid - (optional) is a type of string
              file_uid = secrets.value["file_uid"]
              # secret_id - (required) is a type of string
              secret_id = secrets.value["secret_id"]
              # secret_name - (optional) is a type of string
              secret_name = secrets.value["secret_name"]
            }
          }

        }
      }

      dynamic "log_driver" {
        for_each = task_spec.value.log_driver
        content {
          # name - (required) is a type of string
          name = log_driver.value["name"]
          # options - (optional) is a type of map of string
          options = log_driver.value["options"]
        }
      }

      dynamic "placement" {
        for_each = task_spec.value.placement
        content {
          # constraints - (optional) is a type of set of string
          constraints = placement.value["constraints"]
          # prefs - (optional) is a type of set of string
          prefs = placement.value["prefs"]

          dynamic "platforms" {
            for_each = placement.value.platforms
            content {
              # architecture - (required) is a type of string
              architecture = platforms.value["architecture"]
              # os - (required) is a type of string
              os = platforms.value["os"]
            }
          }

        }
      }

      dynamic "resources" {
        for_each = task_spec.value.resources
        content {

          dynamic "limits" {
            for_each = resources.value.limits
            content {
              # memory_bytes - (optional) is a type of number
              memory_bytes = limits.value["memory_bytes"]
              # nano_cpus - (optional) is a type of number
              nano_cpus = limits.value["nano_cpus"]

              dynamic "generic_resources" {
                for_each = limits.value.generic_resources
                content {
                  # discrete_resources_spec - (optional) is a type of set of string
                  discrete_resources_spec = generic_resources.value["discrete_resources_spec"]
                  # named_resources_spec - (optional) is a type of set of string
                  named_resources_spec = generic_resources.value["named_resources_spec"]
                }
              }

            }
          }

          dynamic "reservation" {
            for_each = resources.value.reservation
            content {
              # memory_bytes - (optional) is a type of number
              memory_bytes = reservation.value["memory_bytes"]
              # nano_cpus - (optional) is a type of number
              nano_cpus = reservation.value["nano_cpus"]

              dynamic "generic_resources" {
                for_each = reservation.value.generic_resources
                content {
                  # discrete_resources_spec - (optional) is a type of set of string
                  discrete_resources_spec = generic_resources.value["discrete_resources_spec"]
                  # named_resources_spec - (optional) is a type of set of string
                  named_resources_spec = generic_resources.value["named_resources_spec"]
                }
              }

            }
          }

        }
      }

    }
  }

  dynamic "update_config" {
    for_each = var.update_config
    content {
      # delay - (optional) is a type of string
      delay = update_config.value["delay"]
      # failure_action - (optional) is a type of string
      failure_action = update_config.value["failure_action"]
      # max_failure_ratio - (optional) is a type of string
      max_failure_ratio = update_config.value["max_failure_ratio"]
      # monitor - (optional) is a type of string
      monitor = update_config.value["monitor"]
      # order - (optional) is a type of string
      order = update_config.value["order"]
      # parallelism - (optional) is a type of number
      parallelism = update_config.value["parallelism"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = docker_service.this.id
}

output "this" {
  value = docker_service.this
}
```

[top](#index)