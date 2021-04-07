# tencentcloud_kubernetes_scale_worker

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
module "tencentcloud_kubernetes_scale_worker" {
  source = "./modules/tencentcloud/r/tencentcloud_kubernetes_scale_worker"

  # cluster_id - (required) is a type of string
  cluster_id = null
  # docker_graph_path - (optional) is a type of string
  docker_graph_path = null
  # extra_args - (optional) is a type of list of string
  extra_args = []
  # labels - (optional) is a type of map of string
  labels = {}
  # mount_target - (optional) is a type of string
  mount_target = null
  # unschedulable - (optional) is a type of number
  unschedulable = null

  data_disk = [{
    auto_format_and_mount = null
    disk_size             = null
    disk_type             = null
    file_system           = null
    mount_target          = null
  }]

  worker_config = [{
    availability_zone = null
    cam_role_name     = null
    count             = null
    data_disk = [{
      disk_size   = null
      disk_type   = null
      snapshot_id = null
    }]
    disaster_recover_group_ids              = []
    enhanced_monitor_service                = null
    enhanced_security_service               = null
    hostname                                = null
    instance_charge_type                    = null
    instance_charge_type_prepaid_period     = null
    instance_charge_type_prepaid_renew_flag = null
    instance_name                           = null
    instance_type                           = null
    internet_charge_type                    = null
    internet_max_bandwidth_out              = null
    key_ids                                 = []
    password                                = null
    public_ip_assigned                      = null
    security_group_ids                      = []
    subnet_id                               = null
    system_disk_size                        = null
    system_disk_type                        = null
    user_data                               = null
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

variable "docker_graph_path" {
  description = "(optional) - Docker graph path. Default is `/var/lib/docker`."
  type        = string
  default     = null
}

variable "extra_args" {
  description = "(optional) - Custom parameter information related to the node."
  type        = list(string)
  default     = null
}

variable "labels" {
  description = "(optional) - Labels of kubernetes scale worker created nodes."
  type        = map(string)
  default     = null
}

variable "mount_target" {
  description = "(optional) - Mount target. Default is not mounting."
  type        = string
  default     = null
}

variable "unschedulable" {
  description = "(optional) - Sets whether the joining node participates in the schedule. Default is '0'. Participate in scheduling."
  type        = number
  default     = null
}

variable "data_disk" {
  description = "nested block: NestingList, min items: 0, max items: 11"
  type = set(object(
    {
      auto_format_and_mount = bool
      disk_size             = number
      disk_type             = string
      file_system           = string
      mount_target          = string
    }
  ))
  default = []
}

variable "worker_config" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      availability_zone = string
      cam_role_name     = string
      count             = number
      data_disk = list(object(
        {
          disk_size   = number
          disk_type   = string
          snapshot_id = string
        }
      ))
      disaster_recover_group_ids              = list(string)
      enhanced_monitor_service                = bool
      enhanced_security_service               = bool
      hostname                                = string
      instance_charge_type                    = string
      instance_charge_type_prepaid_period     = number
      instance_charge_type_prepaid_renew_flag = string
      instance_name                           = string
      instance_type                           = string
      internet_charge_type                    = string
      internet_max_bandwidth_out              = number
      key_ids                                 = list(string)
      password                                = string
      public_ip_assigned                      = bool
      security_group_ids                      = list(string)
      subnet_id                               = string
      system_disk_size                        = number
      system_disk_type                        = string
      user_data                               = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_kubernetes_scale_worker" "this" {
  # cluster_id - (required) is a type of string
  cluster_id = var.cluster_id
  # docker_graph_path - (optional) is a type of string
  docker_graph_path = var.docker_graph_path
  # extra_args - (optional) is a type of list of string
  extra_args = var.extra_args
  # labels - (optional) is a type of map of string
  labels = var.labels
  # mount_target - (optional) is a type of string
  mount_target = var.mount_target
  # unschedulable - (optional) is a type of number
  unschedulable = var.unschedulable

  dynamic "data_disk" {
    for_each = var.data_disk
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

  dynamic "worker_config" {
    for_each = var.worker_config
    content {
      # availability_zone - (optional) is a type of string
      availability_zone = worker_config.value["availability_zone"]
      # cam_role_name - (optional) is a type of string
      cam_role_name = worker_config.value["cam_role_name"]
      # count - (optional) is a type of number
      count = worker_config.value["count"]
      # disaster_recover_group_ids - (optional) is a type of list of string
      disaster_recover_group_ids = worker_config.value["disaster_recover_group_ids"]
      # enhanced_monitor_service - (optional) is a type of bool
      enhanced_monitor_service = worker_config.value["enhanced_monitor_service"]
      # enhanced_security_service - (optional) is a type of bool
      enhanced_security_service = worker_config.value["enhanced_security_service"]
      # hostname - (optional) is a type of string
      hostname = worker_config.value["hostname"]
      # instance_charge_type - (optional) is a type of string
      instance_charge_type = worker_config.value["instance_charge_type"]
      # instance_charge_type_prepaid_period - (optional) is a type of number
      instance_charge_type_prepaid_period = worker_config.value["instance_charge_type_prepaid_period"]
      # instance_charge_type_prepaid_renew_flag - (optional) is a type of string
      instance_charge_type_prepaid_renew_flag = worker_config.value["instance_charge_type_prepaid_renew_flag"]
      # instance_name - (optional) is a type of string
      instance_name = worker_config.value["instance_name"]
      # instance_type - (required) is a type of string
      instance_type = worker_config.value["instance_type"]
      # internet_charge_type - (optional) is a type of string
      internet_charge_type = worker_config.value["internet_charge_type"]
      # internet_max_bandwidth_out - (optional) is a type of number
      internet_max_bandwidth_out = worker_config.value["internet_max_bandwidth_out"]
      # key_ids - (optional) is a type of list of string
      key_ids = worker_config.value["key_ids"]
      # password - (optional) is a type of string
      password = worker_config.value["password"]
      # public_ip_assigned - (optional) is a type of bool
      public_ip_assigned = worker_config.value["public_ip_assigned"]
      # security_group_ids - (optional) is a type of list of string
      security_group_ids = worker_config.value["security_group_ids"]
      # subnet_id - (required) is a type of string
      subnet_id = worker_config.value["subnet_id"]
      # system_disk_size - (optional) is a type of number
      system_disk_size = worker_config.value["system_disk_size"]
      # system_disk_type - (optional) is a type of string
      system_disk_type = worker_config.value["system_disk_type"]
      # user_data - (optional) is a type of string
      user_data = worker_config.value["user_data"]

      dynamic "data_disk" {
        for_each = worker_config.value.data_disk
        content {
          # disk_size - (optional) is a type of number
          disk_size = data_disk.value["disk_size"]
          # disk_type - (optional) is a type of string
          disk_type = data_disk.value["disk_type"]
          # snapshot_id - (optional) is a type of string
          snapshot_id = data_disk.value["snapshot_id"]
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
  value       = tencentcloud_kubernetes_scale_worker.this.id
}

output "worker_instances_list" {
  description = "returns a list of object"
  value       = tencentcloud_kubernetes_scale_worker.this.worker_instances_list
}

output "this" {
  value = tencentcloud_kubernetes_scale_worker.this
}
```

[top](#index)