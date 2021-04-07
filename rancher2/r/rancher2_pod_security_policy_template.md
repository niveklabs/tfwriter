# rancher2_pod_security_policy_template

[back](../rancher2.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    rancher2 = ">= 1.13.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "rancher2_pod_security_policy_template" {
  source = "./modules/rancher2/r/rancher2_pod_security_policy_template"

  # allow_privilege_escalation - (optional) is a type of bool
  allow_privilege_escalation = null
  # allowed_capabilities - (optional) is a type of list of string
  allowed_capabilities = []
  # allowed_proc_mount_types - (optional) is a type of list of string
  allowed_proc_mount_types = []
  # allowed_unsafe_sysctls - (optional) is a type of list of string
  allowed_unsafe_sysctls = []
  # annotations - (optional) is a type of map of string
  annotations = {}
  # default_add_capabilities - (optional) is a type of list of string
  default_add_capabilities = []
  # default_allow_privilege_escalation - (optional) is a type of bool
  default_allow_privilege_escalation = null
  # description - (optional) is a type of string
  description = null
  # forbidden_sysctls - (optional) is a type of list of string
  forbidden_sysctls = []
  # host_ipc - (optional) is a type of bool
  host_ipc = null
  # host_network - (optional) is a type of bool
  host_network = null
  # host_pid - (optional) is a type of bool
  host_pid = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null
  # privileged - (optional) is a type of bool
  privileged = null
  # read_only_root_filesystem - (optional) is a type of bool
  read_only_root_filesystem = null
  # required_drop_capabilities - (optional) is a type of list of string
  required_drop_capabilities = []
  # volumes - (optional) is a type of list of string
  volumes = []

  allowed_csi_driver = [{
    name = null
  }]

  allowed_flex_volume = [{
    driver = null
  }]

  allowed_host_path = [{
    path_prefix = null
    read_only   = null
  }]

  fs_group = [{
    range = [{
      max = null
      min = null
    }]
    rule = null
  }]

  host_port = [{
    max = null
    min = null
  }]

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

  runtime_class = [{
    allowed_runtime_class_names = []
    default_runtime_class_name  = null
  }]

  se_linux = [{
    rule = null
    se_linux_option = [{
      level = null
      role  = null
      type  = null
      user  = null
    }]
  }]

  supplemental_group = [{
    range = [{
      max = null
      min = null
    }]
    rule = null
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
variable "allow_privilege_escalation" {
  description = "(optional) - allowPrivilegeEscalation determines if a pod can request to allow privilege escalation. If unspecified, defaults to true."
  type        = bool
  default     = null
}

variable "allowed_capabilities" {
  description = "(optional) - allowedCapabilities is a list of capabilities that can be requested to add to the container. Capabilities in this field may be added at the pod author's discretion. You must not list a capability in both allowedCapabilities and requiredDropCapabilities."
  type        = list(string)
  default     = null
}

variable "allowed_proc_mount_types" {
  description = "(optional) - AllowedProcMountTypes is a whitelist of allowed ProcMountTypes. Empty or nil indicates that only the DefaultProcMountType may be used. This requires the ProcMountType feature flag to be enabled."
  type        = list(string)
  default     = null
}

variable "allowed_unsafe_sysctls" {
  description = "(optional) - allowedUnsafeSysctls is a list of explicitly allowed unsafe sysctls, defaults to none. Each entry is either a plain sysctl name or ends in \"*\" in which case it is considered as a prefix of allowed sysctls. Single * means all unsafe sysctls are allowed. Kubelet has to whitelist all allowed unsafe sysctls explicitly to avoid rejection."
  type        = list(string)
  default     = null
}

variable "annotations" {
  description = "(optional) - Annotations of the resource"
  type        = map(string)
  default     = null
}

variable "default_add_capabilities" {
  description = "(optional) - defaultAddCapabilities is the default set of capabilities that will be added to the container unless the pod spec specifically drops the capability.  You may not list a capability in both defaultAddCapabilities and requiredDropCapabilities. Capabilities added here are implicitly allowed, and need not be included in the allowedCapabilities list."
  type        = list(string)
  default     = null
}

variable "default_allow_privilege_escalation" {
  description = "(optional) - defaultAllowPrivilegeEscalation controls the default setting for whether a process can gain more privileges than its parent process."
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional) - Pod Security Policy template policy description"
  type        = string
  default     = null
}

variable "forbidden_sysctls" {
  description = "(optional) - forbiddenSysctls is a list of explicitly forbidden sysctls, defaults to none. Each entry is either a plain sysctl name or ends in \"*\" in which case it is considered as a prefix of forbidden sysctls. Single * means all sysctls are forbidden."
  type        = list(string)
  default     = null
}

variable "host_ipc" {
  description = "(optional) - hostIPC determines if the policy allows the use of HostIPC in the pod spec."
  type        = bool
  default     = null
}

variable "host_network" {
  description = "(optional) - hostNetwork determines if the policy allows the use of HostNetwork in the pod spec."
  type        = bool
  default     = null
}

variable "host_pid" {
  description = "(optional) - hostPID determines if the policy allows the use of HostPID in the pod spec."
  type        = bool
  default     = null
}

variable "labels" {
  description = "(optional) - Labels of the resource"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - Pod Security Policy template policy name"
  type        = string
}

variable "privileged" {
  description = "(optional) - privileged determines if a pod can request to be run as privileged."
  type        = bool
  default     = null
}

variable "read_only_root_filesystem" {
  description = "(optional) - readOnlyRootFilesystem when set to true will force containers to run with a read only root file system.  If the container specifically requests to run with a non-read only root file system the PSP should deny the pod. If set to false the container may run with a read only root file system if it wishes but it will not be forced to."
  type        = bool
  default     = null
}

variable "required_drop_capabilities" {
  description = "(optional) - requiredDropCapabilities are the capabilities that will be dropped from the container.  These are required to be dropped and cannot be added."
  type        = list(string)
  default     = null
}

variable "volumes" {
  description = "(optional) - volumes is a white list of allowed volume plugins. Empty indicates that no volumes may be used. To allow all volumes you may use '*'"
  type        = list(string)
  default     = null
}

variable "allowed_csi_driver" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "allowed_flex_volume" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      driver = string
    }
  ))
  default = []
}

variable "allowed_host_path" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      path_prefix = string
      read_only   = bool
    }
  ))
  default = []
}

variable "fs_group" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
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
  default = []
}

variable "host_port" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      max = number
      min = number
    }
  ))
  default = []
}

variable "run_as_group" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
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
  default = []
}

variable "run_as_user" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
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
  default = []
}

variable "runtime_class" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      allowed_runtime_class_names = list(string)
      default_runtime_class_name  = string
    }
  ))
  default = []
}

variable "se_linux" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      rule = string
      se_linux_option = list(object(
        {
          level = string
          role  = string
          type  = string
          user  = string
        }
      ))
    }
  ))
  default = []
}

variable "supplemental_group" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
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
resource "rancher2_pod_security_policy_template" "this" {
  # allow_privilege_escalation - (optional) is a type of bool
  allow_privilege_escalation = var.allow_privilege_escalation
  # allowed_capabilities - (optional) is a type of list of string
  allowed_capabilities = var.allowed_capabilities
  # allowed_proc_mount_types - (optional) is a type of list of string
  allowed_proc_mount_types = var.allowed_proc_mount_types
  # allowed_unsafe_sysctls - (optional) is a type of list of string
  allowed_unsafe_sysctls = var.allowed_unsafe_sysctls
  # annotations - (optional) is a type of map of string
  annotations = var.annotations
  # default_add_capabilities - (optional) is a type of list of string
  default_add_capabilities = var.default_add_capabilities
  # default_allow_privilege_escalation - (optional) is a type of bool
  default_allow_privilege_escalation = var.default_allow_privilege_escalation
  # description - (optional) is a type of string
  description = var.description
  # forbidden_sysctls - (optional) is a type of list of string
  forbidden_sysctls = var.forbidden_sysctls
  # host_ipc - (optional) is a type of bool
  host_ipc = var.host_ipc
  # host_network - (optional) is a type of bool
  host_network = var.host_network
  # host_pid - (optional) is a type of bool
  host_pid = var.host_pid
  # labels - (optional) is a type of map of string
  labels = var.labels
  # name - (required) is a type of string
  name = var.name
  # privileged - (optional) is a type of bool
  privileged = var.privileged
  # read_only_root_filesystem - (optional) is a type of bool
  read_only_root_filesystem = var.read_only_root_filesystem
  # required_drop_capabilities - (optional) is a type of list of string
  required_drop_capabilities = var.required_drop_capabilities
  # volumes - (optional) is a type of list of string
  volumes = var.volumes

  dynamic "allowed_csi_driver" {
    for_each = var.allowed_csi_driver
    content {
      # name - (required) is a type of string
      name = allowed_csi_driver.value["name"]
    }
  }

  dynamic "allowed_flex_volume" {
    for_each = var.allowed_flex_volume
    content {
      # driver - (required) is a type of string
      driver = allowed_flex_volume.value["driver"]
    }
  }

  dynamic "allowed_host_path" {
    for_each = var.allowed_host_path
    content {
      # path_prefix - (required) is a type of string
      path_prefix = allowed_host_path.value["path_prefix"]
      # read_only - (optional) is a type of bool
      read_only = allowed_host_path.value["read_only"]
    }
  }

  dynamic "fs_group" {
    for_each = var.fs_group
    content {
      # rule - (optional) is a type of string
      rule = fs_group.value["rule"]

      dynamic "range" {
        for_each = fs_group.value.range
        content {
          # max - (required) is a type of number
          max = range.value["max"]
          # min - (required) is a type of number
          min = range.value["min"]
        }
      }

    }
  }

  dynamic "host_port" {
    for_each = var.host_port
    content {
      # max - (required) is a type of number
      max = host_port.value["max"]
      # min - (required) is a type of number
      min = host_port.value["min"]
    }
  }

  dynamic "run_as_group" {
    for_each = var.run_as_group
    content {
      # rule - (required) is a type of string
      rule = run_as_group.value["rule"]

      dynamic "range" {
        for_each = run_as_group.value.range
        content {
          # max - (required) is a type of number
          max = range.value["max"]
          # min - (required) is a type of number
          min = range.value["min"]
        }
      }

    }
  }

  dynamic "run_as_user" {
    for_each = var.run_as_user
    content {
      # rule - (required) is a type of string
      rule = run_as_user.value["rule"]

      dynamic "range" {
        for_each = run_as_user.value.range
        content {
          # max - (required) is a type of number
          max = range.value["max"]
          # min - (required) is a type of number
          min = range.value["min"]
        }
      }

    }
  }

  dynamic "runtime_class" {
    for_each = var.runtime_class
    content {
      # allowed_runtime_class_names - (required) is a type of list of string
      allowed_runtime_class_names = runtime_class.value["allowed_runtime_class_names"]
      # default_runtime_class_name - (optional) is a type of string
      default_runtime_class_name = runtime_class.value["default_runtime_class_name"]
    }
  }

  dynamic "se_linux" {
    for_each = var.se_linux
    content {
      # rule - (required) is a type of string
      rule = se_linux.value["rule"]

      dynamic "se_linux_option" {
        for_each = se_linux.value.se_linux_option
        content {
          # level - (optional) is a type of string
          level = se_linux_option.value["level"]
          # role - (optional) is a type of string
          role = se_linux_option.value["role"]
          # type - (optional) is a type of string
          type = se_linux_option.value["type"]
          # user - (optional) is a type of string
          user = se_linux_option.value["user"]
        }
      }

    }
  }

  dynamic "supplemental_group" {
    for_each = var.supplemental_group
    content {
      # rule - (optional) is a type of string
      rule = supplemental_group.value["rule"]

      dynamic "range" {
        for_each = supplemental_group.value.range
        content {
          # max - (required) is a type of number
          max = range.value["max"]
          # min - (required) is a type of number
          min = range.value["min"]
        }
      }

    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "allow_privilege_escalation" {
  description = "returns a bool"
  value       = rancher2_pod_security_policy_template.this.allow_privilege_escalation
}

output "annotations" {
  description = "returns a map of string"
  value       = rancher2_pod_security_policy_template.this.annotations
}

output "description" {
  description = "returns a string"
  value       = rancher2_pod_security_policy_template.this.description
}

output "host_ipc" {
  description = "returns a bool"
  value       = rancher2_pod_security_policy_template.this.host_ipc
}

output "host_network" {
  description = "returns a bool"
  value       = rancher2_pod_security_policy_template.this.host_network
}

output "host_pid" {
  description = "returns a bool"
  value       = rancher2_pod_security_policy_template.this.host_pid
}

output "id" {
  description = "returns a string"
  value       = rancher2_pod_security_policy_template.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = rancher2_pod_security_policy_template.this.labels
}

output "privileged" {
  description = "returns a bool"
  value       = rancher2_pod_security_policy_template.this.privileged
}

output "read_only_root_filesystem" {
  description = "returns a bool"
  value       = rancher2_pod_security_policy_template.this.read_only_root_filesystem
}

output "volumes" {
  description = "returns a list of string"
  value       = rancher2_pod_security_policy_template.this.volumes
}

output "this" {
  value = rancher2_pod_security_policy_template.this
}
```

[top](#index)