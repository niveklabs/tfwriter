# alicloud_cs_kubernetes

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
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_cs_kubernetes" {
  source = "./modules/alicloud/r/alicloud_cs_kubernetes"

  # api_audiences - (optional) is a type of list of string
  api_audiences = []
  # availability_zone - (optional) is a type of string
  availability_zone = null
  # client_cert - (optional) is a type of string
  client_cert = null
  # client_key - (optional) is a type of string
  client_key = null
  # cluster_ca_cert - (optional) is a type of string
  cluster_ca_cert = null
  # cluster_domain - (optional) is a type of string
  cluster_domain = null
  # cluster_network_type - (optional) is a type of string
  cluster_network_type = null
  # cpu_policy - (optional) is a type of string
  cpu_policy = null
  # custom_san - (optional) is a type of string
  custom_san = null
  # deletion_protection - (optional) is a type of bool
  deletion_protection = null
  # enable_ssh - (optional) is a type of bool
  enable_ssh = null
  # exclude_autoscaler_nodes - (optional) is a type of bool
  exclude_autoscaler_nodes = null
  # force_update - (optional) is a type of bool
  force_update = null
  # image_id - (optional) is a type of string
  image_id = null
  # install_cloud_monitor - (optional) is a type of bool
  install_cloud_monitor = null
  # is_enterprise_security_group - (optional) is a type of bool
  is_enterprise_security_group = null
  # key_name - (optional) is a type of string
  key_name = null
  # kms_encrypted_password - (optional) is a type of string
  kms_encrypted_password = null
  # kms_encryption_context - (optional) is a type of map of string
  kms_encryption_context = {}
  # kube_config - (optional) is a type of string
  kube_config = null
  # load_balancer_spec - (optional) is a type of string
  load_balancer_spec = null
  # master_auto_renew - (optional) is a type of bool
  master_auto_renew = null
  # master_auto_renew_period - (optional) is a type of number
  master_auto_renew_period = null
  # master_disk_category - (optional) is a type of string
  master_disk_category = null
  # master_disk_performance_level - (optional) is a type of string
  master_disk_performance_level = null
  # master_disk_size - (optional) is a type of number
  master_disk_size = null
  # master_disk_snapshot_policy_id - (optional) is a type of string
  master_disk_snapshot_policy_id = null
  # master_instance_charge_type - (optional) is a type of string
  master_instance_charge_type = null
  # master_instance_type - (optional) is a type of string
  master_instance_type = null
  # master_instance_types - (required) is a type of list of string
  master_instance_types = []
  # master_period - (optional) is a type of number
  master_period = null
  # master_period_unit - (optional) is a type of string
  master_period_unit = null
  # master_vswitch_ids - (required) is a type of list of string
  master_vswitch_ids = []
  # name - (optional) is a type of string
  name = null
  # name_prefix - (optional) is a type of string
  name_prefix = null
  # new_nat_gateway - (optional) is a type of bool
  new_nat_gateway = null
  # node_cidr_mask - (optional) is a type of number
  node_cidr_mask = null
  # node_name_mode - (optional) is a type of string
  node_name_mode = null
  # node_port_range - (optional) is a type of string
  node_port_range = null
  # nodes - (optional) is a type of list of string
  nodes = []
  # os_type - (optional) is a type of string
  os_type = null
  # password - (optional) is a type of string
  password = null
  # platform - (optional) is a type of string
  platform = null
  # pod_cidr - (optional) is a type of string
  pod_cidr = null
  # pod_vswitch_ids - (optional) is a type of list of string
  pod_vswitch_ids = []
  # proxy_mode - (optional) is a type of string
  proxy_mode = null
  # rds_instances - (optional) is a type of list of string
  rds_instances = []
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # runtime - (optional) is a type of map of string
  runtime = {}
  # security_group_id - (optional) is a type of string
  security_group_id = null
  # service_account_issuer - (optional) is a type of string
  service_account_issuer = null
  # service_cidr - (optional) is a type of string
  service_cidr = null
  # slb_internet_enabled - (optional) is a type of bool
  slb_internet_enabled = null
  # tags - (optional) is a type of map of string
  tags = {}
  # timezone - (optional) is a type of string
  timezone = null
  # user_ca - (optional) is a type of string
  user_ca = null
  # user_data - (optional) is a type of string
  user_data = null
  # version - (optional) is a type of string
  version = null
  # vswitch_id - (optional) is a type of string
  vswitch_id = null
  # vswitch_ids - (optional) is a type of list of string
  vswitch_ids = []
  # worker_auto_renew - (optional) is a type of bool
  worker_auto_renew = null
  # worker_auto_renew_period - (optional) is a type of number
  worker_auto_renew_period = null
  # worker_data_disk_category - (optional) is a type of string
  worker_data_disk_category = null
  # worker_data_disk_size - (optional) is a type of number
  worker_data_disk_size = null
  # worker_disk_category - (optional) is a type of string
  worker_disk_category = null
  # worker_disk_performance_level - (optional) is a type of string
  worker_disk_performance_level = null
  # worker_disk_size - (optional) is a type of number
  worker_disk_size = null
  # worker_disk_snapshot_policy_id - (optional) is a type of string
  worker_disk_snapshot_policy_id = null
  # worker_instance_charge_type - (optional) is a type of string
  worker_instance_charge_type = null
  # worker_instance_type - (optional) is a type of string
  worker_instance_type = null
  # worker_instance_types - (required) is a type of list of string
  worker_instance_types = []
  # worker_number - (required) is a type of number
  worker_number = null
  # worker_numbers - (optional) is a type of list of number
  worker_numbers = []
  # worker_period - (optional) is a type of number
  worker_period = null
  # worker_period_unit - (optional) is a type of string
  worker_period_unit = null
  # worker_vswitch_ids - (required) is a type of list of string
  worker_vswitch_ids = []

  addons = [{
    config   = null
    disabled = null
    name     = null
  }]

  log_config = [{
    project = null
    type    = null
  }]

  taints = [{
    effect = null
    key    = null
    value  = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]

  worker_data_disks = [{
    auto_snapshot_policy_id = null
    category                = null
    device                  = null
    encrypted               = null
    kms_key_id              = null
    name                    = null
    performance_level       = null
    size                    = null
    snapshot_id             = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "api_audiences" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "availability_zone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "client_cert" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "client_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cluster_ca_cert" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cluster_domain" {
  description = "(optional) - cluster local domain"
  type        = string
  default     = null
}

variable "cluster_network_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cpu_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "custom_san" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "deletion_protection" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_ssh" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "exclude_autoscaler_nodes" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "force_update" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "image_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "install_cloud_monitor" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "is_enterprise_security_group" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "key_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "kms_encrypted_password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "kms_encryption_context" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "kube_config" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "load_balancer_spec" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "master_auto_renew" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "master_auto_renew_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "master_disk_category" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "master_disk_performance_level" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "master_disk_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "master_disk_snapshot_policy_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "master_instance_charge_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "master_instance_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "master_instance_types" {
  description = "(required)"
  type        = list(string)
}

variable "master_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "master_period_unit" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "master_vswitch_ids" {
  description = "(required)"
  type        = list(string)
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "new_nat_gateway" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "node_cidr_mask" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "node_name_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "node_port_range" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "nodes" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "os_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "platform" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pod_cidr" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pod_vswitch_ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "proxy_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rds_instances" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "resource_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "runtime" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "security_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_account_issuer" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_cidr" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "slb_internet_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "timezone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_ca" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_data" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vswitch_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vswitch_ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "worker_auto_renew" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "worker_auto_renew_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "worker_data_disk_category" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "worker_data_disk_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "worker_disk_category" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "worker_disk_performance_level" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "worker_disk_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "worker_disk_snapshot_policy_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "worker_instance_charge_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "worker_instance_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "worker_instance_types" {
  description = "(required)"
  type        = list(string)
}

variable "worker_number" {
  description = "(required)"
  type        = number
}

variable "worker_numbers" {
  description = "(optional)"
  type        = list(number)
  default     = null
}

variable "worker_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "worker_period_unit" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "worker_vswitch_ids" {
  description = "(required)"
  type        = list(string)
}

variable "addons" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      config   = string
      disabled = bool
      name     = string
    }
  ))
  default = []
}

variable "log_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      project = string
      type    = string
    }
  ))
  default = []
}

variable "taints" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      effect = string
      key    = string
      value  = string
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

variable "worker_data_disks" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      auto_snapshot_policy_id = string
      category                = string
      device                  = string
      encrypted               = string
      kms_key_id              = string
      name                    = string
      performance_level       = string
      size                    = string
      snapshot_id             = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_cs_kubernetes" "this" {
  api_audiences                  = var.api_audiences
  availability_zone              = var.availability_zone
  client_cert                    = var.client_cert
  client_key                     = var.client_key
  cluster_ca_cert                = var.cluster_ca_cert
  cluster_domain                 = var.cluster_domain
  cluster_network_type           = var.cluster_network_type
  cpu_policy                     = var.cpu_policy
  custom_san                     = var.custom_san
  deletion_protection            = var.deletion_protection
  enable_ssh                     = var.enable_ssh
  exclude_autoscaler_nodes       = var.exclude_autoscaler_nodes
  force_update                   = var.force_update
  image_id                       = var.image_id
  install_cloud_monitor          = var.install_cloud_monitor
  is_enterprise_security_group   = var.is_enterprise_security_group
  key_name                       = var.key_name
  kms_encrypted_password         = var.kms_encrypted_password
  kms_encryption_context         = var.kms_encryption_context
  kube_config                    = var.kube_config
  load_balancer_spec             = var.load_balancer_spec
  master_auto_renew              = var.master_auto_renew
  master_auto_renew_period       = var.master_auto_renew_period
  master_disk_category           = var.master_disk_category
  master_disk_performance_level  = var.master_disk_performance_level
  master_disk_size               = var.master_disk_size
  master_disk_snapshot_policy_id = var.master_disk_snapshot_policy_id
  master_instance_charge_type    = var.master_instance_charge_type
  master_instance_type           = var.master_instance_type
  master_instance_types          = var.master_instance_types
  master_period                  = var.master_period
  master_period_unit             = var.master_period_unit
  master_vswitch_ids             = var.master_vswitch_ids
  name                           = var.name
  name_prefix                    = var.name_prefix
  new_nat_gateway                = var.new_nat_gateway
  node_cidr_mask                 = var.node_cidr_mask
  node_name_mode                 = var.node_name_mode
  node_port_range                = var.node_port_range
  nodes                          = var.nodes
  os_type                        = var.os_type
  password                       = var.password
  platform                       = var.platform
  pod_cidr                       = var.pod_cidr
  pod_vswitch_ids                = var.pod_vswitch_ids
  proxy_mode                     = var.proxy_mode
  rds_instances                  = var.rds_instances
  resource_group_id              = var.resource_group_id
  runtime                        = var.runtime
  security_group_id              = var.security_group_id
  service_account_issuer         = var.service_account_issuer
  service_cidr                   = var.service_cidr
  slb_internet_enabled           = var.slb_internet_enabled
  tags                           = var.tags
  timezone                       = var.timezone
  user_ca                        = var.user_ca
  user_data                      = var.user_data
  version                        = var.version
  vswitch_id                     = var.vswitch_id
  vswitch_ids                    = var.vswitch_ids
  worker_auto_renew              = var.worker_auto_renew
  worker_auto_renew_period       = var.worker_auto_renew_period
  worker_data_disk_category      = var.worker_data_disk_category
  worker_data_disk_size          = var.worker_data_disk_size
  worker_disk_category           = var.worker_disk_category
  worker_disk_performance_level  = var.worker_disk_performance_level
  worker_disk_size               = var.worker_disk_size
  worker_disk_snapshot_policy_id = var.worker_disk_snapshot_policy_id
  worker_instance_charge_type    = var.worker_instance_charge_type
  worker_instance_type           = var.worker_instance_type
  worker_instance_types          = var.worker_instance_types
  worker_number                  = var.worker_number
  worker_numbers                 = var.worker_numbers
  worker_period                  = var.worker_period
  worker_period_unit             = var.worker_period_unit
  worker_vswitch_ids             = var.worker_vswitch_ids

  dynamic "addons" {
    for_each = var.addons
    content {
      config   = addons.value["config"]
      disabled = addons.value["disabled"]
      name     = addons.value["name"]
    }
  }

  dynamic "log_config" {
    for_each = var.log_config
    content {
      project = log_config.value["project"]
      type    = log_config.value["type"]
    }
  }

  dynamic "taints" {
    for_each = var.taints
    content {
      effect = taints.value["effect"]
      key    = taints.value["key"]
      value  = taints.value["value"]
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

  dynamic "worker_data_disks" {
    for_each = var.worker_data_disks
    content {
      auto_snapshot_policy_id = worker_data_disks.value["auto_snapshot_policy_id"]
      category                = worker_data_disks.value["category"]
      device                  = worker_data_disks.value["device"]
      encrypted               = worker_data_disks.value["encrypted"]
      kms_key_id              = worker_data_disks.value["kms_key_id"]
      name                    = worker_data_disks.value["name"]
      performance_level       = worker_data_disks.value["performance_level"]
      size                    = worker_data_disks.value["size"]
      snapshot_id             = worker_data_disks.value["snapshot_id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "availability_zone" {
  description = "returns a string"
  value       = alicloud_cs_kubernetes.this.availability_zone
}

output "certificate_authority" {
  description = "returns a map of string"
  value       = alicloud_cs_kubernetes.this.certificate_authority
}

output "connections" {
  description = "returns a map of string"
  value       = alicloud_cs_kubernetes.this.connections
}

output "id" {
  description = "returns a string"
  value       = alicloud_cs_kubernetes.this.id
}

output "is_enterprise_security_group" {
  description = "returns a bool"
  value       = alicloud_cs_kubernetes.this.is_enterprise_security_group
}

output "master_nodes" {
  description = "returns a list of object"
  value       = alicloud_cs_kubernetes.this.master_nodes
}

output "name" {
  description = "returns a string"
  value       = alicloud_cs_kubernetes.this.name
}

output "nat_gateway_id" {
  description = "returns a string"
  value       = alicloud_cs_kubernetes.this.nat_gateway_id
}

output "resource_group_id" {
  description = "returns a string"
  value       = alicloud_cs_kubernetes.this.resource_group_id
}

output "security_group_id" {
  description = "returns a string"
  value       = alicloud_cs_kubernetes.this.security_group_id
}

output "slb_id" {
  description = "returns a string"
  value       = alicloud_cs_kubernetes.this.slb_id
}

output "slb_internet" {
  description = "returns a string"
  value       = alicloud_cs_kubernetes.this.slb_internet
}

output "slb_intranet" {
  description = "returns a string"
  value       = alicloud_cs_kubernetes.this.slb_intranet
}

output "version" {
  description = "returns a string"
  value       = alicloud_cs_kubernetes.this.version
}

output "vpc_id" {
  description = "returns a string"
  value       = alicloud_cs_kubernetes.this.vpc_id
}

output "worker_nodes" {
  description = "returns a list of object"
  value       = alicloud_cs_kubernetes.this.worker_nodes
}

output "worker_ram_role_name" {
  description = "returns a string"
  value       = alicloud_cs_kubernetes.this.worker_ram_role_name
}

output "this" {
  value = alicloud_cs_kubernetes.this
}
```

[top](#index)