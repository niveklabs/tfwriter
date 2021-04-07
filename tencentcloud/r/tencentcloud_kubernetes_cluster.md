# tencentcloud_kubernetes_cluster

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
module "tencentcloud_kubernetes_cluster" {
  source = "./modules/tencentcloud/r/tencentcloud_kubernetes_cluster"

  # claim_expired_seconds - (optional) is a type of number
  claim_expired_seconds = null
  # cluster_as_enabled - (optional) is a type of bool
  cluster_as_enabled = null
  # cluster_cidr - (optional) is a type of string
  cluster_cidr = null
  # cluster_deploy_type - (optional) is a type of string
  cluster_deploy_type = null
  # cluster_desc - (optional) is a type of string
  cluster_desc = null
  # cluster_internet - (optional) is a type of bool
  cluster_internet = null
  # cluster_intranet - (optional) is a type of bool
  cluster_intranet = null
  # cluster_intranet_subnet_id - (optional) is a type of string
  cluster_intranet_subnet_id = null
  # cluster_ipvs - (optional) is a type of bool
  cluster_ipvs = null
  # cluster_max_pod_num - (optional) is a type of number
  cluster_max_pod_num = null
  # cluster_max_service_num - (optional) is a type of number
  cluster_max_service_num = null
  # cluster_name - (optional) is a type of string
  cluster_name = null
  # cluster_os - (optional) is a type of string
  cluster_os = null
  # cluster_os_type - (optional) is a type of string
  cluster_os_type = null
  # cluster_version - (optional) is a type of string
  cluster_version = null
  # container_runtime - (optional) is a type of string
  container_runtime = null
  # deletion_protection - (optional) is a type of bool
  deletion_protection = null
  # docker_graph_path - (optional) is a type of string
  docker_graph_path = null
  # eni_subnet_ids - (optional) is a type of list of string
  eni_subnet_ids = []
  # extra_args - (optional) is a type of list of string
  extra_args = []
  # ignore_cluster_cidr_conflict - (optional) is a type of bool
  ignore_cluster_cidr_conflict = null
  # is_non_static_ip_mode - (optional) is a type of bool
  is_non_static_ip_mode = null
  # kube_proxy_mode - (optional) is a type of string
  kube_proxy_mode = null
  # labels - (optional) is a type of map of string
  labels = {}
  # managed_cluster_internet_security_policies - (optional) is a type of list of string
  managed_cluster_internet_security_policies = []
  # mount_target - (optional) is a type of string
  mount_target = null
  # network_type - (optional) is a type of string
  network_type = null
  # node_name_type - (optional) is a type of string
  node_name_type = null
  # project_id - (optional) is a type of number
  project_id = null
  # service_cidr - (optional) is a type of string
  service_cidr = null
  # tags - (optional) is a type of map of string
  tags = {}
  # unschedulable - (optional) is a type of number
  unschedulable = null
  # vpc_id - (required) is a type of string
  vpc_id = null

  cluster_extra_args = [{
    kube_apiserver          = []
    kube_controller_manager = []
    kube_scheduler          = []
  }]

  master_config = [{
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

  node_pool_global_config = [{
    expander                       = null
    ignore_daemon_sets_utilization = null
    is_scale_in_enabled            = null
    max_concurrent_scale_in        = null
    scale_in_delay                 = null
    scale_in_unneeded_time         = null
    scale_in_utilization_threshold = null
    skip_nodes_with_local_storage  = null
    skip_nodes_with_system_pods    = null
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
variable "claim_expired_seconds" {
  description = "(optional) - Claim expired seconds to recycle ENI. This field can only set when field `network_type` is 'VPC-CNI'. `claim_expired_seconds` must greater or equal than 300 and less than 15768000."
  type        = number
  default     = null
}

variable "cluster_as_enabled" {
  description = "(optional) - Indicates whether to enable cluster node auto scaler."
  type        = bool
  default     = null
}

variable "cluster_cidr" {
  description = "(optional) - A network address block of the cluster. Different from vpc cidr and cidr of other clusters within this vpc. Must be in  10./192.168/172.[16-31] segments."
  type        = string
  default     = null
}

variable "cluster_deploy_type" {
  description = "(optional) - Deployment type of the cluster, the available values include: 'MANAGED_CLUSTER' and 'INDEPENDENT_CLUSTER'. Default is 'MANAGED_CLUSTER'."
  type        = string
  default     = null
}

variable "cluster_desc" {
  description = "(optional) - Description of the cluster."
  type        = string
  default     = null
}

variable "cluster_internet" {
  description = "(optional) - Open internet access or not."
  type        = bool
  default     = null
}

variable "cluster_intranet" {
  description = "(optional) - Open intranet access or not."
  type        = bool
  default     = null
}

variable "cluster_intranet_subnet_id" {
  description = "(optional) - Subnet id who can access this independent cluster, this field must and can only set  when `cluster_intranet` is true. `cluster_intranet_subnet_id` can not modify once be set."
  type        = string
  default     = null
}

variable "cluster_ipvs" {
  description = "(optional) - Indicates whether `ipvs` is enabled. Default is true. False means `iptables` is enabled."
  type        = bool
  default     = null
}

variable "cluster_max_pod_num" {
  description = "(optional) - The maximum number of Pods per node in the cluster. Default is 256. Must be a multiple of 16 and large than 32."
  type        = number
  default     = null
}

variable "cluster_max_service_num" {
  description = "(optional) - The maximum number of services in the cluster. Default is 256. Must be a multiple of 16."
  type        = number
  default     = null
}

variable "cluster_name" {
  description = "(optional) - Name of the cluster."
  type        = string
  default     = null
}

variable "cluster_os" {
  description = "(optional) - Operating system of the cluster, the available values include: 'centos7.2x86_64','centos7.6x86_64','ubuntu16.04.1 LTSx86_64','ubuntu18.04.1 LTSx86_64','tlinux2.4x86_64'. Default is 'ubuntu16.04.1 LTSx86_64'."
  type        = string
  default     = null
}

variable "cluster_os_type" {
  description = "(optional) - Image type of the cluster os, the available values include: 'GENERAL'. Default is 'GENERAL'."
  type        = string
  default     = null
}

variable "cluster_version" {
  description = "(optional) - Version of the cluster, Default is '1.10.5'."
  type        = string
  default     = null
}

variable "container_runtime" {
  description = "(optional) - Runtime type of the cluster, the available values include: 'docker' and 'containerd'. Default is 'docker'."
  type        = string
  default     = null
}

variable "deletion_protection" {
  description = "(optional) - Indicates whether cluster deletion protection is enabled. Default is false."
  type        = bool
  default     = null
}

variable "docker_graph_path" {
  description = "(optional) - Docker graph path. Default is `/var/lib/docker`."
  type        = string
  default     = null
}

variable "eni_subnet_ids" {
  description = "(optional) - Subnet Ids for cluster with VPC-CNI network mode. This field can only set when field `network_type` is 'VPC-CNI'. `eni_subnet_ids` can not empty once be set."
  type        = list(string)
  default     = null
}

variable "extra_args" {
  description = "(optional) - Custom parameter information related to the node."
  type        = list(string)
  default     = null
}

variable "ignore_cluster_cidr_conflict" {
  description = "(optional) - Indicates whether to ignore the cluster cidr conflict error. Default is false."
  type        = bool
  default     = null
}

variable "is_non_static_ip_mode" {
  description = "(optional) - Indicates whether static ip mode is enabled. Default is false."
  type        = bool
  default     = null
}

variable "kube_proxy_mode" {
  description = "(optional) - Cluster kube-proxy mode, the available values include: 'kube-proxy-bpf'. Default is not set.When set to kube-proxy-bpf, cluster version greater than 1.14 and with Tencent Linux 2.4 is required."
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional) - Labels of tke cluster nodes."
  type        = map(string)
  default     = null
}

variable "managed_cluster_internet_security_policies" {
  description = "(optional) - Security policies for managed cluster internet, like:'192.168.1.0/24' or '113.116.51.27', '0.0.0.0/0' means all. This field can only set when field `cluster_deploy_type` is 'MANAGED_CLUSTER' and `cluster_internet` is true. `managed_cluster_internet_security_policies` can not delete or empty once be set."
  type        = list(string)
  default     = null
}

variable "mount_target" {
  description = "(optional) - Mount target. Default is not mounting."
  type        = string
  default     = null
}

variable "network_type" {
  description = "(optional) - Cluster network type, GR or VPC-CNI. Default is GR."
  type        = string
  default     = null
}

variable "node_name_type" {
  description = "(optional) - Node name type of Cluster, the available values include: 'lan-ip' and 'hostname', Default is 'lan-ip'."
  type        = string
  default     = null
}

variable "project_id" {
  description = "(optional) - Project ID, default value is 0."
  type        = number
  default     = null
}

variable "service_cidr" {
  description = "(optional) - A network address block of the service. Different from vpc cidr and cidr of other clusters within this vpc. Must be in  10./192.168/172.[16-31] segments."
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - The tags of the cluster."
  type        = map(string)
  default     = null
}

variable "unschedulable" {
  description = "(optional) - Sets whether the joining node participates in the schedule. Default is '0'. Participate in scheduling."
  type        = number
  default     = null
}

variable "vpc_id" {
  description = "(required) - Vpc Id of the cluster."
  type        = string
}

variable "cluster_extra_args" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      kube_apiserver          = list(string)
      kube_controller_manager = list(string)
      kube_scheduler          = list(string)
    }
  ))
  default = []
}

variable "master_config" {
  description = "nested block: NestingList, min items: 0, max items: 0"
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
  default = []
}

variable "node_pool_global_config" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      expander                       = string
      ignore_daemon_sets_utilization = bool
      is_scale_in_enabled            = bool
      max_concurrent_scale_in        = number
      scale_in_delay                 = number
      scale_in_unneeded_time         = number
      scale_in_utilization_threshold = number
      skip_nodes_with_local_storage  = bool
      skip_nodes_with_system_pods    = bool
    }
  ))
  default = []
}

variable "worker_config" {
  description = "nested block: NestingList, min items: 0, max items: 0"
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
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_kubernetes_cluster" "this" {
  claim_expired_seconds                      = var.claim_expired_seconds
  cluster_as_enabled                         = var.cluster_as_enabled
  cluster_cidr                               = var.cluster_cidr
  cluster_deploy_type                        = var.cluster_deploy_type
  cluster_desc                               = var.cluster_desc
  cluster_internet                           = var.cluster_internet
  cluster_intranet                           = var.cluster_intranet
  cluster_intranet_subnet_id                 = var.cluster_intranet_subnet_id
  cluster_ipvs                               = var.cluster_ipvs
  cluster_max_pod_num                        = var.cluster_max_pod_num
  cluster_max_service_num                    = var.cluster_max_service_num
  cluster_name                               = var.cluster_name
  cluster_os                                 = var.cluster_os
  cluster_os_type                            = var.cluster_os_type
  cluster_version                            = var.cluster_version
  container_runtime                          = var.container_runtime
  deletion_protection                        = var.deletion_protection
  docker_graph_path                          = var.docker_graph_path
  eni_subnet_ids                             = var.eni_subnet_ids
  extra_args                                 = var.extra_args
  ignore_cluster_cidr_conflict               = var.ignore_cluster_cidr_conflict
  is_non_static_ip_mode                      = var.is_non_static_ip_mode
  kube_proxy_mode                            = var.kube_proxy_mode
  labels                                     = var.labels
  managed_cluster_internet_security_policies = var.managed_cluster_internet_security_policies
  mount_target                               = var.mount_target
  network_type                               = var.network_type
  node_name_type                             = var.node_name_type
  project_id                                 = var.project_id
  service_cidr                               = var.service_cidr
  tags                                       = var.tags
  unschedulable                              = var.unschedulable
  vpc_id                                     = var.vpc_id

  dynamic "cluster_extra_args" {
    for_each = var.cluster_extra_args
    content {
      kube_apiserver          = cluster_extra_args.value["kube_apiserver"]
      kube_controller_manager = cluster_extra_args.value["kube_controller_manager"]
      kube_scheduler          = cluster_extra_args.value["kube_scheduler"]
    }
  }

  dynamic "master_config" {
    for_each = var.master_config
    content {
      availability_zone                       = master_config.value["availability_zone"]
      cam_role_name                           = master_config.value["cam_role_name"]
      count                                   = master_config.value["count"]
      disaster_recover_group_ids              = master_config.value["disaster_recover_group_ids"]
      enhanced_monitor_service                = master_config.value["enhanced_monitor_service"]
      enhanced_security_service               = master_config.value["enhanced_security_service"]
      hostname                                = master_config.value["hostname"]
      instance_charge_type                    = master_config.value["instance_charge_type"]
      instance_charge_type_prepaid_period     = master_config.value["instance_charge_type_prepaid_period"]
      instance_charge_type_prepaid_renew_flag = master_config.value["instance_charge_type_prepaid_renew_flag"]
      instance_name                           = master_config.value["instance_name"]
      instance_type                           = master_config.value["instance_type"]
      internet_charge_type                    = master_config.value["internet_charge_type"]
      internet_max_bandwidth_out              = master_config.value["internet_max_bandwidth_out"]
      key_ids                                 = master_config.value["key_ids"]
      password                                = master_config.value["password"]
      public_ip_assigned                      = master_config.value["public_ip_assigned"]
      security_group_ids                      = master_config.value["security_group_ids"]
      subnet_id                               = master_config.value["subnet_id"]
      system_disk_size                        = master_config.value["system_disk_size"]
      system_disk_type                        = master_config.value["system_disk_type"]
      user_data                               = master_config.value["user_data"]

      dynamic "data_disk" {
        for_each = master_config.value.data_disk
        content {
          disk_size   = data_disk.value["disk_size"]
          disk_type   = data_disk.value["disk_type"]
          snapshot_id = data_disk.value["snapshot_id"]
        }
      }

    }
  }

  dynamic "node_pool_global_config" {
    for_each = var.node_pool_global_config
    content {
      expander                       = node_pool_global_config.value["expander"]
      ignore_daemon_sets_utilization = node_pool_global_config.value["ignore_daemon_sets_utilization"]
      is_scale_in_enabled            = node_pool_global_config.value["is_scale_in_enabled"]
      max_concurrent_scale_in        = node_pool_global_config.value["max_concurrent_scale_in"]
      scale_in_delay                 = node_pool_global_config.value["scale_in_delay"]
      scale_in_unneeded_time         = node_pool_global_config.value["scale_in_unneeded_time"]
      scale_in_utilization_threshold = node_pool_global_config.value["scale_in_utilization_threshold"]
      skip_nodes_with_local_storage  = node_pool_global_config.value["skip_nodes_with_local_storage"]
      skip_nodes_with_system_pods    = node_pool_global_config.value["skip_nodes_with_system_pods"]
    }
  }

  dynamic "worker_config" {
    for_each = var.worker_config
    content {
      availability_zone                       = worker_config.value["availability_zone"]
      cam_role_name                           = worker_config.value["cam_role_name"]
      count                                   = worker_config.value["count"]
      disaster_recover_group_ids              = worker_config.value["disaster_recover_group_ids"]
      enhanced_monitor_service                = worker_config.value["enhanced_monitor_service"]
      enhanced_security_service               = worker_config.value["enhanced_security_service"]
      hostname                                = worker_config.value["hostname"]
      instance_charge_type                    = worker_config.value["instance_charge_type"]
      instance_charge_type_prepaid_period     = worker_config.value["instance_charge_type_prepaid_period"]
      instance_charge_type_prepaid_renew_flag = worker_config.value["instance_charge_type_prepaid_renew_flag"]
      instance_name                           = worker_config.value["instance_name"]
      instance_type                           = worker_config.value["instance_type"]
      internet_charge_type                    = worker_config.value["internet_charge_type"]
      internet_max_bandwidth_out              = worker_config.value["internet_max_bandwidth_out"]
      key_ids                                 = worker_config.value["key_ids"]
      password                                = worker_config.value["password"]
      public_ip_assigned                      = worker_config.value["public_ip_assigned"]
      security_group_ids                      = worker_config.value["security_group_ids"]
      subnet_id                               = worker_config.value["subnet_id"]
      system_disk_size                        = worker_config.value["system_disk_size"]
      system_disk_type                        = worker_config.value["system_disk_type"]
      user_data                               = worker_config.value["user_data"]

      dynamic "data_disk" {
        for_each = worker_config.value.data_disk
        content {
          disk_size   = data_disk.value["disk_size"]
          disk_type   = data_disk.value["disk_type"]
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
output "certification_authority" {
  description = "returns a string"
  value       = tencentcloud_kubernetes_cluster.this.certification_authority
}

output "cluster_external_endpoint" {
  description = "returns a string"
  value       = tencentcloud_kubernetes_cluster.this.cluster_external_endpoint
}

output "cluster_node_num" {
  description = "returns a number"
  value       = tencentcloud_kubernetes_cluster.this.cluster_node_num
}

output "domain" {
  description = "returns a string"
  value       = tencentcloud_kubernetes_cluster.this.domain
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_kubernetes_cluster.this.id
}

output "kube_config" {
  description = "returns a string"
  value       = tencentcloud_kubernetes_cluster.this.kube_config
}

output "password" {
  description = "returns a string"
  value       = tencentcloud_kubernetes_cluster.this.password
}

output "pgw_endpoint" {
  description = "returns a string"
  value       = tencentcloud_kubernetes_cluster.this.pgw_endpoint
}

output "security_policy" {
  description = "returns a list of string"
  value       = tencentcloud_kubernetes_cluster.this.security_policy
}

output "user_name" {
  description = "returns a string"
  value       = tencentcloud_kubernetes_cluster.this.user_name
}

output "worker_instances_list" {
  description = "returns a list of object"
  value       = tencentcloud_kubernetes_cluster.this.worker_instances_list
}

output "this" {
  value = tencentcloud_kubernetes_cluster.this
}
```

[top](#index)