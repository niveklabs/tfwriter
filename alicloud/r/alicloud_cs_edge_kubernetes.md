# alicloud_cs_edge_kubernetes

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
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_cs_edge_kubernetes" {
  source = "./modules/alicloud/r/alicloud_cs_edge_kubernetes"

  # availability_zone - (optional) is a type of string
  availability_zone = null
  # client_cert - (optional) is a type of string
  client_cert = null
  # client_key - (optional) is a type of string
  client_key = null
  # cluster_ca_cert - (optional) is a type of string
  cluster_ca_cert = null
  # deletion_protection - (optional) is a type of bool
  deletion_protection = null
  # install_cloud_monitor - (optional) is a type of bool
  install_cloud_monitor = null
  # is_enterprise_security_group - (optional) is a type of bool
  is_enterprise_security_group = null
  # key_name - (optional) is a type of string
  key_name = null
  # kube_config - (optional) is a type of string
  kube_config = null
  # name - (optional) is a type of string
  name = null
  # name_prefix - (optional) is a type of string
  name_prefix = null
  # new_nat_gateway - (optional) is a type of bool
  new_nat_gateway = null
  # node_cidr_mask - (optional) is a type of number
  node_cidr_mask = null
  # password - (optional) is a type of string
  password = null
  # pod_cidr - (optional) is a type of string
  pod_cidr = null
  # proxy_mode - (optional) is a type of string
  proxy_mode = null
  # rds_instances - (optional) is a type of list of string
  rds_instances = []
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # security_group_id - (optional) is a type of string
  security_group_id = null
  # service_cidr - (optional) is a type of string
  service_cidr = null
  # slb_internet_enabled - (optional) is a type of bool
  slb_internet_enabled = null
  # user_data - (optional) is a type of string
  user_data = null
  # version - (optional) is a type of string
  version = null
  # worker_disk_category - (optional) is a type of string
  worker_disk_category = null
  # worker_disk_size - (optional) is a type of number
  worker_disk_size = null
  # worker_instance_charge_type - (optional) is a type of string
  worker_instance_charge_type = null
  # worker_instance_types - (required) is a type of list of string
  worker_instance_types = []
  # worker_number - (required) is a type of number
  worker_number = null
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
    size                    = null
    snapshot_id             = null
  }]
}
```

[top](#index)

### Variables

```terraform
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

variable "deletion_protection" {
  description = "(optional)"
  type        = bool
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

variable "kube_config" {
  description = "(optional)"
  type        = string
  default     = null
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

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pod_cidr" {
  description = "(optional)"
  type        = string
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

variable "security_group_id" {
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

variable "worker_disk_category" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "worker_disk_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "worker_instance_charge_type" {
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
resource "alicloud_cs_edge_kubernetes" "this" {
  availability_zone            = var.availability_zone
  client_cert                  = var.client_cert
  client_key                   = var.client_key
  cluster_ca_cert              = var.cluster_ca_cert
  deletion_protection          = var.deletion_protection
  install_cloud_monitor        = var.install_cloud_monitor
  is_enterprise_security_group = var.is_enterprise_security_group
  key_name                     = var.key_name
  kube_config                  = var.kube_config
  name                         = var.name
  name_prefix                  = var.name_prefix
  new_nat_gateway              = var.new_nat_gateway
  node_cidr_mask               = var.node_cidr_mask
  password                     = var.password
  pod_cidr                     = var.pod_cidr
  proxy_mode                   = var.proxy_mode
  rds_instances                = var.rds_instances
  resource_group_id            = var.resource_group_id
  security_group_id            = var.security_group_id
  service_cidr                 = var.service_cidr
  slb_internet_enabled         = var.slb_internet_enabled
  user_data                    = var.user_data
  version                      = var.version
  worker_disk_category         = var.worker_disk_category
  worker_disk_size             = var.worker_disk_size
  worker_instance_charge_type  = var.worker_instance_charge_type
  worker_instance_types        = var.worker_instance_types
  worker_number                = var.worker_number
  worker_vswitch_ids           = var.worker_vswitch_ids

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
  value       = alicloud_cs_edge_kubernetes.this.availability_zone
}

output "certificate_authority" {
  description = "returns a map of string"
  value       = alicloud_cs_edge_kubernetes.this.certificate_authority
}

output "connections" {
  description = "returns a map of string"
  value       = alicloud_cs_edge_kubernetes.this.connections
}

output "id" {
  description = "returns a string"
  value       = alicloud_cs_edge_kubernetes.this.id
}

output "is_enterprise_security_group" {
  description = "returns a bool"
  value       = alicloud_cs_edge_kubernetes.this.is_enterprise_security_group
}

output "name" {
  description = "returns a string"
  value       = alicloud_cs_edge_kubernetes.this.name
}

output "nat_gateway_id" {
  description = "returns a string"
  value       = alicloud_cs_edge_kubernetes.this.nat_gateway_id
}

output "security_group_id" {
  description = "returns a string"
  value       = alicloud_cs_edge_kubernetes.this.security_group_id
}

output "slb_internet" {
  description = "returns a string"
  value       = alicloud_cs_edge_kubernetes.this.slb_internet
}

output "slb_intranet" {
  description = "returns a string"
  value       = alicloud_cs_edge_kubernetes.this.slb_intranet
}

output "version" {
  description = "returns a string"
  value       = alicloud_cs_edge_kubernetes.this.version
}

output "vpc_id" {
  description = "returns a string"
  value       = alicloud_cs_edge_kubernetes.this.vpc_id
}

output "worker_nodes" {
  description = "returns a list of object"
  value       = alicloud_cs_edge_kubernetes.this.worker_nodes
}

output "this" {
  value = alicloud_cs_edge_kubernetes.this
}
```

[top](#index)