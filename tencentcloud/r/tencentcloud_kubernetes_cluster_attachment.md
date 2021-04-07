# tencentcloud_kubernetes_cluster_attachment

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tencentcloud = ">= 1.56.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tencentcloud_kubernetes_cluster_attachment" {
  source = "./modules/tencentcloud/r/tencentcloud_kubernetes_cluster_attachment"

  # cluster_id - (required) is a type of string
  cluster_id = null
  # hostname - (optional) is a type of string
  hostname = null
  # instance_id - (required) is a type of string
  instance_id = null
  # key_ids - (optional) is a type of list of string
  key_ids = []
  # labels - (optional) is a type of map of string
  labels = {}
  # password - (optional) is a type of string
  password = null
  # unschedulable - (optional) is a type of number
  unschedulable = null

  worker_config = [{
    data_disk = [{
      auto_format_and_mount = null
      disk_size             = null
      disk_type             = null
      file_system           = null
      mount_target          = null
    }]
    docker_graph_path = null
    extra_args        = []
    is_schedule       = null
    mount_target      = null
    user_data         = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cluster_id" {
  description = "(required) - ID of the cluster."
  type        = string
}

variable "hostname" {
  description = "(optional) - The host name of the attached instance. Dot (.) and dash (-) cannot be used as the first and last characters of HostName and cannot be used consecutively. Windows example: The length of the name character is [2, 15], letters (capitalization is not restricted), numbers and dashes (-) are allowed, dots (.) are not supported, and not all numbers are allowed. Examples of other types (Linux, etc.): The character length is [2, 60], and multiple dots are allowed. There is a segment between the dots. Each segment allows letters (with no limitation on capitalization), numbers and dashes (-)."
  type        = string
  default     = null
}

variable "instance_id" {
  description = "(required) - ID of the CVM instance, this cvm will reinstall the system."
  type        = string
}

variable "key_ids" {
  description = "(optional) - The key pair to use for the instance, it looks like skey-16jig7tx, it should be set if `password` not set."
  type        = list(string)
  default     = null
}

variable "labels" {
  description = "(optional) - Labels of tke attachment exits CVM."
  type        = map(string)
  default     = null
}

variable "password" {
  description = "(optional) - Password to access, should be set if `key_ids` not set."
  type        = string
  default     = null
}

variable "unschedulable" {
  description = "(optional) - Sets whether the joining node participates in the schedule. Default is '0'. Participate in scheduling."
  type        = number
  default     = null
}

variable "worker_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      data_disk = list(object(
        {
          auto_format_and_mount = bool
          disk_size             = number
          disk_type             = string
          file_system           = string
          mount_target          = string
        }
      ))
      docker_graph_path = string
      extra_args        = list(string)
      is_schedule       = bool
      mount_target      = string
      user_data         = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_kubernetes_cluster_attachment" "this" {
  # cluster_id - (required) is a type of string
  cluster_id = var.cluster_id
  # hostname - (optional) is a type of string
  hostname = var.hostname
  # instance_id - (required) is a type of string
  instance_id = var.instance_id
  # key_ids - (optional) is a type of list of string
  key_ids = var.key_ids
  # labels - (optional) is a type of map of string
  labels = var.labels
  # password - (optional) is a type of string
  password = var.password
  # unschedulable - (optional) is a type of number
  unschedulable = var.unschedulable

  dynamic "worker_config" {
    for_each = var.worker_config
    content {
      # docker_graph_path - (optional) is a type of string
      docker_graph_path = worker_config.value["docker_graph_path"]
      # extra_args - (optional) is a type of list of string
      extra_args = worker_config.value["extra_args"]
      # is_schedule - (optional) is a type of bool
      is_schedule = worker_config.value["is_schedule"]
      # mount_target - (optional) is a type of string
      mount_target = worker_config.value["mount_target"]
      # user_data - (optional) is a type of string
      user_data = worker_config.value["user_data"]

      dynamic "data_disk" {
        for_each = worker_config.value.data_disk
        content {
          # auto_format_and_mount - (optional) is a type of bool
          auto_format_and_mount = data_disk.value["auto_format_and_mount"]
          # disk_size - (optional) is a type of number
          disk_size = data_disk.value["disk_size"]
          # disk_type - (optional) is a type of string
          disk_type = data_disk.value["disk_type"]
          # file_system - (optional) is a type of string
          file_system = data_disk.value["file_system"]
          # mount_target - (optional) is a type of string
          mount_target = data_disk.value["mount_target"]
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
  value       = tencentcloud_kubernetes_cluster_attachment.this.id
}

output "security_groups" {
  description = "returns a set of string"
  value       = tencentcloud_kubernetes_cluster_attachment.this.security_groups
}

output "state" {
  description = "returns a string"
  value       = tencentcloud_kubernetes_cluster_attachment.this.state
}

output "this" {
  value = tencentcloud_kubernetes_cluster_attachment.this
}
```

[top](#index)