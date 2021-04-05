# stackpath_compute_workload

[back](../stackpath.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    stackpath = ">= 1.3.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "stackpath_compute_workload" {
  source = "./modules/stackpath/r/stackpath_compute_workload"

  # annotations - (optional) is a type of map of string
  annotations = {}
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null
  # slug - (required) is a type of string
  slug = null

  container = [{
    command = []
    env = [{
      key          = null
      secret_value = null
      value        = null
    }]
    image = null
    liveness_probe = [{
      failure_threshold = null
      http_get = [{
        http_headers = {}
        path         = null
        port         = null
        scheme       = null
      }]
      initial_delay_seconds = null
      period_seconds        = null
      success_threshold     = null
      tcp_socket = [{
        port = null
      }]
      timeout_seconds = null
    }]
    name = null
    port = [{
      enable_implicit_network_policy = null
      name                           = null
      port                           = null
      protocol                       = null
    }]
    readiness_probe = [{
      failure_threshold = null
      http_get = [{
        http_headers = {}
        path         = null
        port         = null
        scheme       = null
      }]
      initial_delay_seconds = null
      period_seconds        = null
      success_threshold     = null
      tcp_socket = [{
        port = null
      }]
      timeout_seconds = null
    }]
    resources = [{
      requests = {}
    }]
    volume_mount = [{
      mount_path = null
      slug       = null
    }]
  }]

  image_pull_credentials = [{
    docker_registry = [{
      email    = null
      password = null
      server   = null
      username = null
    }]
  }]

  instances = [{
    container = [{
      command = []
      env = [{
        key          = null
        secret_value = null
        value        = null
      }]
      image = null
      liveness_probe = [{
        failure_threshold = null
        http_get = [{
          http_headers = {}
          path         = null
          port         = null
          scheme       = null
        }]
        initial_delay_seconds = null
        period_seconds        = null
        success_threshold     = null
        tcp_socket = [{
          port = null
        }]
        timeout_seconds = null
      }]
      name = null
      port = [{
        enable_implicit_network_policy = null
        name                           = null
        port                           = null
        protocol                       = null
      }]
      readiness_probe = [{
        failure_threshold = null
        http_get = [{
          http_headers = {}
          path         = null
          port         = null
          scheme       = null
        }]
        initial_delay_seconds = null
        period_seconds        = null
        success_threshold     = null
        tcp_socket = [{
          port = null
        }]
        timeout_seconds = null
      }]
      resources = [{
        requests = {}
      }]
      volume_mount = [{
        mount_path = null
        slug       = null
      }]
    }]
    external_ip_address = null
    ip_address          = null
    location = [{
      city             = null
      city_code        = null
      continent        = null
      continent_code   = null
      country          = null
      country_code     = null
      latitude         = null
      longitude        = null
      name             = null
      region           = null
      region_code      = null
      subdivision      = null
      subdivision_code = null
    }]
    message = null
    metadata = [{
      annotations = {}
      labels      = {}
    }]
    name = null
    network_interface = [{
      gateway            = null
      ip_address         = null
      ip_address_aliases = []
      network            = null
    }]
    phase  = null
    reason = null
    virtual_machine = [{
      image = null
      liveness_probe = [{
        failure_threshold = null
        http_get = [{
          http_headers = {}
          path         = null
          port         = null
          scheme       = null
        }]
        initial_delay_seconds = null
        period_seconds        = null
        success_threshold     = null
        tcp_socket = [{
          port = null
        }]
        timeout_seconds = null
      }]
      name = null
      port = [{
        enable_implicit_network_policy = null
        name                           = null
        port                           = null
        protocol                       = null
      }]
      readiness_probe = [{
        failure_threshold = null
        http_get = [{
          http_headers = {}
          path         = null
          port         = null
          scheme       = null
        }]
        initial_delay_seconds = null
        period_seconds        = null
        success_threshold     = null
        tcp_socket = [{
          port = null
        }]
        timeout_seconds = null
      }]
      resources = [{
        requests = {}
      }]
      user_data = null
      volume_mount = [{
        mount_path = null
        slug       = null
      }]
    }]
  }]

  network_interface = [{
    network = null
  }]

  target = [{
    deployment_scope = null
    max_replicas     = null
    min_replicas     = null
    name             = null
    scale_settings = [{
      metrics = [{
        average_utilization = null
        average_value       = null
        metric              = null
      }]
    }]
    selector = [{
      key      = null
      operator = null
      values   = []
    }]
  }]

  virtual_machine = [{
    image = null
    liveness_probe = [{
      failure_threshold = null
      http_get = [{
        http_headers = {}
        path         = null
        port         = null
        scheme       = null
      }]
      initial_delay_seconds = null
      period_seconds        = null
      success_threshold     = null
      tcp_socket = [{
        port = null
      }]
      timeout_seconds = null
    }]
    name = null
    port = [{
      enable_implicit_network_policy = null
      name                           = null
      port                           = null
      protocol                       = null
    }]
    readiness_probe = [{
      failure_threshold = null
      http_get = [{
        http_headers = {}
        path         = null
        port         = null
        scheme       = null
      }]
      initial_delay_seconds = null
      period_seconds        = null
      success_threshold     = null
      tcp_socket = [{
        port = null
      }]
      timeout_seconds = null
    }]
    resources = [{
      requests = {}
    }]
    user_data = null
    volume_mount = [{
      mount_path = null
      slug       = null
    }]
  }]

  volume_claim = [{
    name = null
    resources = [{
      requests = {}
    }]
    slug = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "annotations" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "labels" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "slug" {
  description = "(required)"
  type        = string
}

variable "container" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      command = list(string)
      env = list(object(
        {
          key          = string
          secret_value = string
          value        = string
        }
      ))
      image = string
      liveness_probe = list(object(
        {
          failure_threshold = number
          http_get = list(object(
            {
              http_headers = map(string)
              path         = string
              port         = number
              scheme       = string
            }
          ))
          initial_delay_seconds = number
          period_seconds        = number
          success_threshold     = number
          tcp_socket = list(object(
            {
              port = number
            }
          ))
          timeout_seconds = number
        }
      ))
      name = string
      port = list(object(
        {
          enable_implicit_network_policy = bool
          name                           = string
          port                           = number
          protocol                       = string
        }
      ))
      readiness_probe = list(object(
        {
          failure_threshold = number
          http_get = list(object(
            {
              http_headers = map(string)
              path         = string
              port         = number
              scheme       = string
            }
          ))
          initial_delay_seconds = number
          period_seconds        = number
          success_threshold     = number
          tcp_socket = list(object(
            {
              port = number
            }
          ))
          timeout_seconds = number
        }
      ))
      resources = list(object(
        {
          requests = map(string)
        }
      ))
      volume_mount = list(object(
        {
          mount_path = string
          slug       = string
        }
      ))
    }
  ))
  default = []
}

variable "image_pull_credentials" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      docker_registry = list(object(
        {
          email    = string
          password = string
          server   = string
          username = string
        }
      ))
    }
  ))
  default = []
}

variable "instances" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      container = list(object(
        {
          command = list(string)
          env = list(object(
            {
              key          = string
              secret_value = string
              value        = string
            }
          ))
          image = string
          liveness_probe = list(object(
            {
              failure_threshold = number
              http_get = list(object(
                {
                  http_headers = map(string)
                  path         = string
                  port         = number
                  scheme       = string
                }
              ))
              initial_delay_seconds = number
              period_seconds        = number
              success_threshold     = number
              tcp_socket = list(object(
                {
                  port = number
                }
              ))
              timeout_seconds = number
            }
          ))
          name = string
          port = list(object(
            {
              enable_implicit_network_policy = bool
              name                           = string
              port                           = number
              protocol                       = string
            }
          ))
          readiness_probe = list(object(
            {
              failure_threshold = number
              http_get = list(object(
                {
                  http_headers = map(string)
                  path         = string
                  port         = number
                  scheme       = string
                }
              ))
              initial_delay_seconds = number
              period_seconds        = number
              success_threshold     = number
              tcp_socket = list(object(
                {
                  port = number
                }
              ))
              timeout_seconds = number
            }
          ))
          resources = list(object(
            {
              requests = map(string)
            }
          ))
          volume_mount = list(object(
            {
              mount_path = string
              slug       = string
            }
          ))
        }
      ))
      external_ip_address = string
      ip_address          = string
      location = list(object(
        {
          city             = string
          city_code        = string
          continent        = string
          continent_code   = string
          country          = string
          country_code     = string
          latitude         = number
          longitude        = number
          name             = string
          region           = string
          region_code      = string
          subdivision      = string
          subdivision_code = string
        }
      ))
      message = string
      metadata = list(object(
        {
          annotations = map(string)
          labels      = map(string)
        }
      ))
      name = string
      network_interface = list(object(
        {
          gateway            = string
          ip_address         = string
          ip_address_aliases = list(string)
          network            = string
        }
      ))
      phase  = string
      reason = string
      virtual_machine = list(object(
        {
          image = string
          liveness_probe = list(object(
            {
              failure_threshold = number
              http_get = list(object(
                {
                  http_headers = map(string)
                  path         = string
                  port         = number
                  scheme       = string
                }
              ))
              initial_delay_seconds = number
              period_seconds        = number
              success_threshold     = number
              tcp_socket = list(object(
                {
                  port = number
                }
              ))
              timeout_seconds = number
            }
          ))
          name = string
          port = list(object(
            {
              enable_implicit_network_policy = bool
              name                           = string
              port                           = number
              protocol                       = string
            }
          ))
          readiness_probe = list(object(
            {
              failure_threshold = number
              http_get = list(object(
                {
                  http_headers = map(string)
                  path         = string
                  port         = number
                  scheme       = string
                }
              ))
              initial_delay_seconds = number
              period_seconds        = number
              success_threshold     = number
              tcp_socket = list(object(
                {
                  port = number
                }
              ))
              timeout_seconds = number
            }
          ))
          resources = list(object(
            {
              requests = map(string)
            }
          ))
          user_data = string
          volume_mount = list(object(
            {
              mount_path = string
              slug       = string
            }
          ))
        }
      ))
    }
  ))
  default = []
}

variable "network_interface" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      network = string
    }
  ))
}

variable "target" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      deployment_scope = string
      max_replicas     = number
      min_replicas     = number
      name             = string
      scale_settings = list(object(
        {
          metrics = list(object(
            {
              average_utilization = number
              average_value       = string
              metric              = string
            }
          ))
        }
      ))
      selector = list(object(
        {
          key      = string
          operator = string
          values   = list(string)
        }
      ))
    }
  ))
}

variable "virtual_machine" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      image = string
      liveness_probe = list(object(
        {
          failure_threshold = number
          http_get = list(object(
            {
              http_headers = map(string)
              path         = string
              port         = number
              scheme       = string
            }
          ))
          initial_delay_seconds = number
          period_seconds        = number
          success_threshold     = number
          tcp_socket = list(object(
            {
              port = number
            }
          ))
          timeout_seconds = number
        }
      ))
      name = string
      port = list(object(
        {
          enable_implicit_network_policy = bool
          name                           = string
          port                           = number
          protocol                       = string
        }
      ))
      readiness_probe = list(object(
        {
          failure_threshold = number
          http_get = list(object(
            {
              http_headers = map(string)
              path         = string
              port         = number
              scheme       = string
            }
          ))
          initial_delay_seconds = number
          period_seconds        = number
          success_threshold     = number
          tcp_socket = list(object(
            {
              port = number
            }
          ))
          timeout_seconds = number
        }
      ))
      resources = list(object(
        {
          requests = map(string)
        }
      ))
      user_data = string
      volume_mount = list(object(
        {
          mount_path = string
          slug       = string
        }
      ))
    }
  ))
  default = []
}

variable "volume_claim" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
      resources = list(object(
        {
          requests = map(string)
        }
      ))
      slug = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "stackpath_compute_workload" "this" {
  annotations = var.annotations
  labels      = var.labels
  name        = var.name
  slug        = var.slug

  dynamic "container" {
    for_each = var.container
    content {
      command = container.value["command"]
      image   = container.value["image"]
      name    = container.value["name"]

      dynamic "env" {
        for_each = container.value.env
        content {
          key          = env.value["key"]
          secret_value = env.value["secret_value"]
          value        = env.value["value"]
        }
      }

      dynamic "liveness_probe" {
        for_each = container.value.liveness_probe
        content {
          failure_threshold     = liveness_probe.value["failure_threshold"]
          initial_delay_seconds = liveness_probe.value["initial_delay_seconds"]
          period_seconds        = liveness_probe.value["period_seconds"]
          success_threshold     = liveness_probe.value["success_threshold"]
          timeout_seconds       = liveness_probe.value["timeout_seconds"]

          dynamic "http_get" {
            for_each = liveness_probe.value.http_get
            content {
              http_headers = http_get.value["http_headers"]
              path         = http_get.value["path"]
              port         = http_get.value["port"]
              scheme       = http_get.value["scheme"]
            }
          }

          dynamic "tcp_socket" {
            for_each = liveness_probe.value.tcp_socket
            content {
              port = tcp_socket.value["port"]
            }
          }

        }
      }

      dynamic "port" {
        for_each = container.value.port
        content {
          enable_implicit_network_policy = port.value["enable_implicit_network_policy"]
          name                           = port.value["name"]
          port                           = port.value["port"]
          protocol                       = port.value["protocol"]
        }
      }

      dynamic "readiness_probe" {
        for_each = container.value.readiness_probe
        content {
          failure_threshold     = readiness_probe.value["failure_threshold"]
          initial_delay_seconds = readiness_probe.value["initial_delay_seconds"]
          period_seconds        = readiness_probe.value["period_seconds"]
          success_threshold     = readiness_probe.value["success_threshold"]
          timeout_seconds       = readiness_probe.value["timeout_seconds"]

          dynamic "http_get" {
            for_each = readiness_probe.value.http_get
            content {
              http_headers = http_get.value["http_headers"]
              path         = http_get.value["path"]
              port         = http_get.value["port"]
              scheme       = http_get.value["scheme"]
            }
          }

          dynamic "tcp_socket" {
            for_each = readiness_probe.value.tcp_socket
            content {
              port = tcp_socket.value["port"]
            }
          }

        }
      }

      dynamic "resources" {
        for_each = container.value.resources
        content {
          requests = resources.value["requests"]
        }
      }

      dynamic "volume_mount" {
        for_each = container.value.volume_mount
        content {
          mount_path = volume_mount.value["mount_path"]
          slug       = volume_mount.value["slug"]
        }
      }

    }
  }

  dynamic "image_pull_credentials" {
    for_each = var.image_pull_credentials
    content {

      dynamic "docker_registry" {
        for_each = image_pull_credentials.value.docker_registry
        content {
          email    = docker_registry.value["email"]
          password = docker_registry.value["password"]
          server   = docker_registry.value["server"]
          username = docker_registry.value["username"]
        }
      }

    }
  }

  dynamic "instances" {
    for_each = var.instances
    content {
      external_ip_address = instances.value["external_ip_address"]
      ip_address          = instances.value["ip_address"]
      message             = instances.value["message"]
      name                = instances.value["name"]
      phase               = instances.value["phase"]
      reason              = instances.value["reason"]

      dynamic "container" {
        for_each = instances.value.container
        content {
          command = container.value["command"]
          image   = container.value["image"]
          name    = container.value["name"]

          dynamic "env" {
            for_each = container.value.env
            content {
              key          = env.value["key"]
              secret_value = env.value["secret_value"]
              value        = env.value["value"]
            }
          }

          dynamic "liveness_probe" {
            for_each = container.value.liveness_probe
            content {
              failure_threshold     = liveness_probe.value["failure_threshold"]
              initial_delay_seconds = liveness_probe.value["initial_delay_seconds"]
              period_seconds        = liveness_probe.value["period_seconds"]
              success_threshold     = liveness_probe.value["success_threshold"]
              timeout_seconds       = liveness_probe.value["timeout_seconds"]

              dynamic "http_get" {
                for_each = liveness_probe.value.http_get
                content {
                  http_headers = http_get.value["http_headers"]
                  path         = http_get.value["path"]
                  port         = http_get.value["port"]
                  scheme       = http_get.value["scheme"]
                }
              }

              dynamic "tcp_socket" {
                for_each = liveness_probe.value.tcp_socket
                content {
                  port = tcp_socket.value["port"]
                }
              }

            }
          }

          dynamic "port" {
            for_each = container.value.port
            content {
              enable_implicit_network_policy = port.value["enable_implicit_network_policy"]
              name                           = port.value["name"]
              port                           = port.value["port"]
              protocol                       = port.value["protocol"]
            }
          }

          dynamic "readiness_probe" {
            for_each = container.value.readiness_probe
            content {
              failure_threshold     = readiness_probe.value["failure_threshold"]
              initial_delay_seconds = readiness_probe.value["initial_delay_seconds"]
              period_seconds        = readiness_probe.value["period_seconds"]
              success_threshold     = readiness_probe.value["success_threshold"]
              timeout_seconds       = readiness_probe.value["timeout_seconds"]

              dynamic "http_get" {
                for_each = readiness_probe.value.http_get
                content {
                  http_headers = http_get.value["http_headers"]
                  path         = http_get.value["path"]
                  port         = http_get.value["port"]
                  scheme       = http_get.value["scheme"]
                }
              }

              dynamic "tcp_socket" {
                for_each = readiness_probe.value.tcp_socket
                content {
                  port = tcp_socket.value["port"]
                }
              }

            }
          }

          dynamic "resources" {
            for_each = container.value.resources
            content {
              requests = resources.value["requests"]
            }
          }

          dynamic "volume_mount" {
            for_each = container.value.volume_mount
            content {
              mount_path = volume_mount.value["mount_path"]
              slug       = volume_mount.value["slug"]
            }
          }

        }
      }

      dynamic "location" {
        for_each = instances.value.location
        content {
          city             = location.value["city"]
          city_code        = location.value["city_code"]
          continent        = location.value["continent"]
          continent_code   = location.value["continent_code"]
          country          = location.value["country"]
          country_code     = location.value["country_code"]
          latitude         = location.value["latitude"]
          longitude        = location.value["longitude"]
          name             = location.value["name"]
          region           = location.value["region"]
          region_code      = location.value["region_code"]
          subdivision      = location.value["subdivision"]
          subdivision_code = location.value["subdivision_code"]
        }
      }

      dynamic "metadata" {
        for_each = instances.value.metadata
        content {
          annotations = metadata.value["annotations"]
          labels      = metadata.value["labels"]
        }
      }

      dynamic "network_interface" {
        for_each = instances.value.network_interface
        content {
          gateway            = network_interface.value["gateway"]
          ip_address         = network_interface.value["ip_address"]
          ip_address_aliases = network_interface.value["ip_address_aliases"]
          network            = network_interface.value["network"]
        }
      }

      dynamic "virtual_machine" {
        for_each = instances.value.virtual_machine
        content {
          image     = virtual_machine.value["image"]
          name      = virtual_machine.value["name"]
          user_data = virtual_machine.value["user_data"]

          dynamic "liveness_probe" {
            for_each = virtual_machine.value.liveness_probe
            content {
              failure_threshold     = liveness_probe.value["failure_threshold"]
              initial_delay_seconds = liveness_probe.value["initial_delay_seconds"]
              period_seconds        = liveness_probe.value["period_seconds"]
              success_threshold     = liveness_probe.value["success_threshold"]
              timeout_seconds       = liveness_probe.value["timeout_seconds"]

              dynamic "http_get" {
                for_each = liveness_probe.value.http_get
                content {
                  http_headers = http_get.value["http_headers"]
                  path         = http_get.value["path"]
                  port         = http_get.value["port"]
                  scheme       = http_get.value["scheme"]
                }
              }

              dynamic "tcp_socket" {
                for_each = liveness_probe.value.tcp_socket
                content {
                  port = tcp_socket.value["port"]
                }
              }

            }
          }

          dynamic "port" {
            for_each = virtual_machine.value.port
            content {
              enable_implicit_network_policy = port.value["enable_implicit_network_policy"]
              name                           = port.value["name"]
              port                           = port.value["port"]
              protocol                       = port.value["protocol"]
            }
          }

          dynamic "readiness_probe" {
            for_each = virtual_machine.value.readiness_probe
            content {
              failure_threshold     = readiness_probe.value["failure_threshold"]
              initial_delay_seconds = readiness_probe.value["initial_delay_seconds"]
              period_seconds        = readiness_probe.value["period_seconds"]
              success_threshold     = readiness_probe.value["success_threshold"]
              timeout_seconds       = readiness_probe.value["timeout_seconds"]

              dynamic "http_get" {
                for_each = readiness_probe.value.http_get
                content {
                  http_headers = http_get.value["http_headers"]
                  path         = http_get.value["path"]
                  port         = http_get.value["port"]
                  scheme       = http_get.value["scheme"]
                }
              }

              dynamic "tcp_socket" {
                for_each = readiness_probe.value.tcp_socket
                content {
                  port = tcp_socket.value["port"]
                }
              }

            }
          }

          dynamic "resources" {
            for_each = virtual_machine.value.resources
            content {
              requests = resources.value["requests"]
            }
          }

          dynamic "volume_mount" {
            for_each = virtual_machine.value.volume_mount
            content {
              mount_path = volume_mount.value["mount_path"]
              slug       = volume_mount.value["slug"]
            }
          }

        }
      }

    }
  }

  dynamic "network_interface" {
    for_each = var.network_interface
    content {
      network = network_interface.value["network"]
    }
  }

  dynamic "target" {
    for_each = var.target
    content {
      deployment_scope = target.value["deployment_scope"]
      max_replicas     = target.value["max_replicas"]
      min_replicas     = target.value["min_replicas"]
      name             = target.value["name"]

      dynamic "scale_settings" {
        for_each = target.value.scale_settings
        content {

          dynamic "metrics" {
            for_each = scale_settings.value.metrics
            content {
              average_utilization = metrics.value["average_utilization"]
              average_value       = metrics.value["average_value"]
              metric              = metrics.value["metric"]
            }
          }

        }
      }

      dynamic "selector" {
        for_each = target.value.selector
        content {
          key      = selector.value["key"]
          operator = selector.value["operator"]
          values   = selector.value["values"]
        }
      }

    }
  }

  dynamic "virtual_machine" {
    for_each = var.virtual_machine
    content {
      image     = virtual_machine.value["image"]
      name      = virtual_machine.value["name"]
      user_data = virtual_machine.value["user_data"]

      dynamic "liveness_probe" {
        for_each = virtual_machine.value.liveness_probe
        content {
          failure_threshold     = liveness_probe.value["failure_threshold"]
          initial_delay_seconds = liveness_probe.value["initial_delay_seconds"]
          period_seconds        = liveness_probe.value["period_seconds"]
          success_threshold     = liveness_probe.value["success_threshold"]
          timeout_seconds       = liveness_probe.value["timeout_seconds"]

          dynamic "http_get" {
            for_each = liveness_probe.value.http_get
            content {
              http_headers = http_get.value["http_headers"]
              path         = http_get.value["path"]
              port         = http_get.value["port"]
              scheme       = http_get.value["scheme"]
            }
          }

          dynamic "tcp_socket" {
            for_each = liveness_probe.value.tcp_socket
            content {
              port = tcp_socket.value["port"]
            }
          }

        }
      }

      dynamic "port" {
        for_each = virtual_machine.value.port
        content {
          enable_implicit_network_policy = port.value["enable_implicit_network_policy"]
          name                           = port.value["name"]
          port                           = port.value["port"]
          protocol                       = port.value["protocol"]
        }
      }

      dynamic "readiness_probe" {
        for_each = virtual_machine.value.readiness_probe
        content {
          failure_threshold     = readiness_probe.value["failure_threshold"]
          initial_delay_seconds = readiness_probe.value["initial_delay_seconds"]
          period_seconds        = readiness_probe.value["period_seconds"]
          success_threshold     = readiness_probe.value["success_threshold"]
          timeout_seconds       = readiness_probe.value["timeout_seconds"]

          dynamic "http_get" {
            for_each = readiness_probe.value.http_get
            content {
              http_headers = http_get.value["http_headers"]
              path         = http_get.value["path"]
              port         = http_get.value["port"]
              scheme       = http_get.value["scheme"]
            }
          }

          dynamic "tcp_socket" {
            for_each = readiness_probe.value.tcp_socket
            content {
              port = tcp_socket.value["port"]
            }
          }

        }
      }

      dynamic "resources" {
        for_each = virtual_machine.value.resources
        content {
          requests = resources.value["requests"]
        }
      }

      dynamic "volume_mount" {
        for_each = virtual_machine.value.volume_mount
        content {
          mount_path = volume_mount.value["mount_path"]
          slug       = volume_mount.value["slug"]
        }
      }

    }
  }

  dynamic "volume_claim" {
    for_each = var.volume_claim
    content {
      name = volume_claim.value["name"]
      slug = volume_claim.value["slug"]

      dynamic "resources" {
        for_each = volume_claim.value.resources
        content {
          requests = resources.value["requests"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "annotations" {
  description = "returns a map of string"
  value       = stackpath_compute_workload.this.annotations
}

output "id" {
  description = "returns a string"
  value       = stackpath_compute_workload.this.id
}

output "this" {
  value = stackpath_compute_workload.this
}
```

[top](#index)