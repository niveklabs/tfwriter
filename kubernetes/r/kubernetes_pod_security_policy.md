# kubernetes_pod_security_policy

[back](../kubernetes.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    kubernetes = ">= 1.13.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "kubernetes_pod_security_policy" {
  source = "./modules/kubernetes/r/kubernetes_pod_security_policy"


  metadata = [{
    annotations      = {}
    generation       = null
    labels           = {}
    name             = null
    resource_version = null
    self_link        = null
    uid              = null
  }]

  spec = [{
    allow_privilege_escalation = null
    allowed_capabilities       = []
    allowed_flex_volumes = [{
      driver = null
    }]
    allowed_host_paths = [{
      path_prefix = null
      read_only   = null
    }]
    allowed_proc_mount_types           = []
    allowed_unsafe_sysctls             = []
    default_add_capabilities           = []
    default_allow_privilege_escalation = null
    forbidden_sysctls                  = []
    fs_group = [{
      range = [{
        max = null
        min = null
      }]
      rule = null
    }]
    host_ipc     = null
    host_network = null
    host_pid     = null
    host_ports = [{
      max = null
      min = null
    }]
    privileged                 = null
    read_only_root_filesystem  = null
    required_drop_capabilities = []
    run_as_group = [{
      range = [{
        max = null
        min = null
      }]
      rule = null
    }]
    run_as_user = [{
      range = [{
        max = null
        min = null
      }]
      rule = null
    }]
    se_linux = [{
      rule = null
      se_linux_options = [{
        level = null
        role  = null
        type  = null
        user  = null
      }]
    }]
    supplemental_groups = [{
      range = [{
        max = null
        min = null
      }]
      rule = null
    }]
    volumes = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "metadata" {
  description = "nested mode: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      annotations      = map(string)
      generation       = number
      labels           = map(string)
      name             = string
      resource_version = string
      self_link        = string
      uid              = string
    }
  ))
}

variable "spec" {
  description = "nested mode: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      allow_privilege_escalation = bool
      allowed_capabilities       = list(string)
      allowed_flex_volumes = list(object(
        {
          driver = string
        }
      ))
      allowed_host_paths = list(object(
        {
          path_prefix = string
          read_only   = bool
        }
      ))
      allowed_proc_mount_types           = list(string)
      allowed_unsafe_sysctls             = list(string)
      default_add_capabilities           = list(string)
      default_allow_privilege_escalation = bool
      forbidden_sysctls                  = list(string)
      fs_group = list(object(
        {
          range = list(object(
            {
              max = number
              min = number
            }
          ))
          rule = string
        }
      ))
      host_ipc     = bool
      host_network = bool
      host_pid     = bool
      host_ports = list(object(
        {
          max = number
          min = number
        }
      ))
      privileged                 = bool
      read_only_root_filesystem  = bool
      required_drop_capabilities = list(string)
      run_as_group = list(object(
        {
          range = list(object(
            {
              max = number
              min = number
            }
          ))
          rule = string
        }
      ))
      run_as_user = list(object(
        {
          range = list(object(
            {
              max = number
              min = number
            }
          ))
          rule = string
        }
      ))
      se_linux = list(object(
        {
          rule = string
          se_linux_options = list(object(
            {
              level = string
              role  = string
              type  = string
              user  = string
            }
          ))
        }
      ))
      supplemental_groups = list(object(
        {
          range = list(object(
            {
              max = number
              min = number
            }
          ))
          rule = string
        }
      ))
      volumes = list(string)
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "kubernetes_pod_security_policy" "this" {

  dynamic "metadata" {
    for_each = var.metadata
    content {
      annotations = metadata.value["annotations"]
      labels      = metadata.value["labels"]
      name        = metadata.value["name"]
    }
  }

  dynamic "spec" {
    for_each = var.spec
    content {
      allow_privilege_escalation         = spec.value["allow_privilege_escalation"]
      allowed_capabilities               = spec.value["allowed_capabilities"]
      allowed_proc_mount_types           = spec.value["allowed_proc_mount_types"]
      allowed_unsafe_sysctls             = spec.value["allowed_unsafe_sysctls"]
      default_add_capabilities           = spec.value["default_add_capabilities"]
      default_allow_privilege_escalation = spec.value["default_allow_privilege_escalation"]
      forbidden_sysctls                  = spec.value["forbidden_sysctls"]
      host_ipc                           = spec.value["host_ipc"]
      host_network                       = spec.value["host_network"]
      host_pid                           = spec.value["host_pid"]
      privileged                         = spec.value["privileged"]
      read_only_root_filesystem          = spec.value["read_only_root_filesystem"]
      required_drop_capabilities         = spec.value["required_drop_capabilities"]
      volumes                            = spec.value["volumes"]

      dynamic "allowed_flex_volumes" {
        for_each = spec.value.allowed_flex_volumes
        content {
          driver = allowed_flex_volumes.value["driver"]
        }
      }

      dynamic "allowed_host_paths" {
        for_each = spec.value.allowed_host_paths
        content {
          path_prefix = allowed_host_paths.value["path_prefix"]
          read_only   = allowed_host_paths.value["read_only"]
        }
      }

      dynamic "fs_group" {
        for_each = spec.value.fs_group
        content {
          rule = fs_group.value["rule"]

          dynamic "range" {
            for_each = fs_group.value.range
            content {
              max = range.value["max"]
              min = range.value["min"]
            }
          }

        }
      }

      dynamic "host_ports" {
        for_each = spec.value.host_ports
        content {
          max = host_ports.value["max"]
          min = host_ports.value["min"]
        }
      }

      dynamic "run_as_group" {
        for_each = spec.value.run_as_group
        content {
          rule = run_as_group.value["rule"]

          dynamic "range" {
            for_each = run_as_group.value.range
            content {
              max = range.value["max"]
              min = range.value["min"]
            }
          }

        }
      }

      dynamic "run_as_user" {
        for_each = spec.value.run_as_user
        content {
          rule = run_as_user.value["rule"]

          dynamic "range" {
            for_each = run_as_user.value.range
            content {
              max = range.value["max"]
              min = range.value["min"]
            }
          }

        }
      }

      dynamic "se_linux" {
        for_each = spec.value.se_linux
        content {
          rule = se_linux.value["rule"]

          dynamic "se_linux_options" {
            for_each = se_linux.value.se_linux_options
            content {
              level = se_linux_options.value["level"]
              role  = se_linux_options.value["role"]
              type  = se_linux_options.value["type"]
              user  = se_linux_options.value["user"]
            }
          }

        }
      }

      dynamic "supplemental_groups" {
        for_each = spec.value.supplemental_groups
        content {
          rule = supplemental_groups.value["rule"]

          dynamic "range" {
            for_each = supplemental_groups.value.range
            content {
              max = range.value["max"]
              min = range.value["min"]
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
output "id" {
  description = "returns a string"
  value       = kubernetes_pod_security_policy.this.id
}

output "this" {
  value = kubernetes_pod_security_policy.this
}
```

[top](#index)