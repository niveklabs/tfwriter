# nutanix_karbon_cluster

[back](../nutanix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nutanix = ">= 1.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nutanix_karbon_cluster" {
  source = "./modules/nutanix/r/nutanix_karbon_cluster"

  # name - (required) is a type of string
  name = null
  # version - (required) is a type of string
  version = null
  # wait_timeout_minutes - (optional) is a type of number
  wait_timeout_minutes = null

  active_passive_config = [{
    external_ipv4_address = null
  }]

  cni_config = [{
    calico_config = [{
      ip_pool_config = [{
        cidr = null
      }]
    }]
    flannel_config = [{

    }]
    node_cidr_mask_size = null
    pod_ipv4_cidr       = null
    service_ipv4_cidr   = null
  }]

  etcd_node_pool = [{
    ahv_config = [{
      cpu                        = null
      disk_mib                   = null
      memory_mib                 = null
      network_uuid               = null
      prism_element_cluster_uuid = null
    }]
    name            = null
    node_os_version = null
    nodes = [{
      hostname     = null
      ipv4_address = null
    }]
    num_instances = null
  }]

  external_lb_config = [{
    external_ipv4_address = null
    master_nodes_config = [{
      ipv4_address   = null
      node_pool_name = null
    }]
  }]

  master_node_pool = [{
    ahv_config = [{
      cpu                        = null
      disk_mib                   = null
      memory_mib                 = null
      network_uuid               = null
      prism_element_cluster_uuid = null
    }]
    name            = null
    node_os_version = null
    nodes = [{
      hostname     = null
      ipv4_address = null
    }]
    num_instances = null
  }]

  private_registry = [{
    registry_name = null
  }]

  single_master_config = [{

  }]

  storage_class_config = [{
    name           = null
    reclaim_policy = null
    volumes_config = [{
      file_system                = null
      flash_mode                 = null
      password                   = null
      prism_element_cluster_uuid = null
      storage_container          = null
      username                   = null
    }]
  }]

  worker_node_pool = [{
    ahv_config = [{
      cpu                        = null
      disk_mib                   = null
      memory_mib                 = null
      network_uuid               = null
      prism_element_cluster_uuid = null
    }]
    name            = null
    node_os_version = null
    nodes = [{
      hostname     = null
      ipv4_address = null
    }]
    num_instances = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "version" {
  description = "(required)"
  type        = string
}

variable "wait_timeout_minutes" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "active_passive_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      external_ipv4_address = string
    }
  ))
  default = []
}

variable "cni_config" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      calico_config = list(object(
        {
          ip_pool_config = list(object(
            {
              cidr = string
            }
          ))
        }
      ))
      flannel_config = list(object(
        {

        }
      ))
      node_cidr_mask_size = number
      pod_ipv4_cidr       = string
      service_ipv4_cidr   = string
    }
  ))
}

variable "etcd_node_pool" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      ahv_config = list(object(
        {
          cpu                        = number
          disk_mib                   = number
          memory_mib                 = number
          network_uuid               = string
          prism_element_cluster_uuid = string
        }
      ))
      name            = string
      node_os_version = string
      nodes = list(object(
        {
          hostname     = string
          ipv4_address = string
        }
      ))
      num_instances = number
    }
  ))
}

variable "external_lb_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      external_ipv4_address = string
      master_nodes_config = set(object(
        {
          ipv4_address   = string
          node_pool_name = string
        }
      ))
    }
  ))
  default = []
}

variable "master_node_pool" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      ahv_config = list(object(
        {
          cpu                        = number
          disk_mib                   = number
          memory_mib                 = number
          network_uuid               = string
          prism_element_cluster_uuid = string
        }
      ))
      name            = string
      node_os_version = string
      nodes = list(object(
        {
          hostname     = string
          ipv4_address = string
        }
      ))
      num_instances = number
    }
  ))
}

variable "private_registry" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      registry_name = string
    }
  ))
  default = []
}

variable "single_master_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {

    }
  ))
  default = []
}

variable "storage_class_config" {
  description = "nested block: NestingSet, min items: 1, max items: 1"
  type = set(object(
    {
      name           = string
      reclaim_policy = string
      volumes_config = list(object(
        {
          file_system                = string
          flash_mode                 = bool
          password                   = string
          prism_element_cluster_uuid = string
          storage_container          = string
          username                   = string
        }
      ))
    }
  ))
}

variable "worker_node_pool" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      ahv_config = list(object(
        {
          cpu                        = number
          disk_mib                   = number
          memory_mib                 = number
          network_uuid               = string
          prism_element_cluster_uuid = string
        }
      ))
      name            = string
      node_os_version = string
      nodes = list(object(
        {
          hostname     = string
          ipv4_address = string
        }
      ))
      num_instances = number
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "nutanix_karbon_cluster" "this" {
  # name - (required) is a type of string
  name = var.name
  # version - (required) is a type of string
  version = var.version
  # wait_timeout_minutes - (optional) is a type of number
  wait_timeout_minutes = var.wait_timeout_minutes

  dynamic "active_passive_config" {
    for_each = var.active_passive_config
    content {
      # external_ipv4_address - (required) is a type of string
      external_ipv4_address = active_passive_config.value["external_ipv4_address"]
    }
  }

  dynamic "cni_config" {
    for_each = var.cni_config
    content {
      # node_cidr_mask_size - (optional) is a type of number
      node_cidr_mask_size = cni_config.value["node_cidr_mask_size"]
      # pod_ipv4_cidr - (optional) is a type of string
      pod_ipv4_cidr = cni_config.value["pod_ipv4_cidr"]
      # service_ipv4_cidr - (optional) is a type of string
      service_ipv4_cidr = cni_config.value["service_ipv4_cidr"]

      dynamic "calico_config" {
        for_each = cni_config.value.calico_config
        content {

          dynamic "ip_pool_config" {
            for_each = calico_config.value.ip_pool_config
            content {
              # cidr - (optional) is a type of string
              cidr = ip_pool_config.value["cidr"]
            }
          }

        }
      }

      dynamic "flannel_config" {
        for_each = cni_config.value.flannel_config
        content {
        }
      }

    }
  }

  dynamic "etcd_node_pool" {
    for_each = var.etcd_node_pool
    content {
      # name - (optional) is a type of string
      name = etcd_node_pool.value["name"]
      # node_os_version - (required) is a type of string
      node_os_version = etcd_node_pool.value["node_os_version"]
      # num_instances - (required) is a type of number
      num_instances = etcd_node_pool.value["num_instances"]

      dynamic "ahv_config" {
        for_each = etcd_node_pool.value.ahv_config
        content {
          # cpu - (optional) is a type of number
          cpu = ahv_config.value["cpu"]
          # disk_mib - (optional) is a type of number
          disk_mib = ahv_config.value["disk_mib"]
          # memory_mib - (optional) is a type of number
          memory_mib = ahv_config.value["memory_mib"]
          # network_uuid - (required) is a type of string
          network_uuid = ahv_config.value["network_uuid"]
          # prism_element_cluster_uuid - (required) is a type of string
          prism_element_cluster_uuid = ahv_config.value["prism_element_cluster_uuid"]
        }
      }

    }
  }

  dynamic "external_lb_config" {
    for_each = var.external_lb_config
    content {
      # external_ipv4_address - (required) is a type of string
      external_ipv4_address = external_lb_config.value["external_ipv4_address"]

      dynamic "master_nodes_config" {
        for_each = external_lb_config.value.master_nodes_config
        content {
          # ipv4_address - (required) is a type of string
          ipv4_address = master_nodes_config.value["ipv4_address"]
          # node_pool_name - (optional) is a type of string
          node_pool_name = master_nodes_config.value["node_pool_name"]
        }
      }

    }
  }

  dynamic "master_node_pool" {
    for_each = var.master_node_pool
    content {
      # name - (optional) is a type of string
      name = master_node_pool.value["name"]
      # node_os_version - (required) is a type of string
      node_os_version = master_node_pool.value["node_os_version"]
      # num_instances - (required) is a type of number
      num_instances = master_node_pool.value["num_instances"]

      dynamic "ahv_config" {
        for_each = master_node_pool.value.ahv_config
        content {
          # cpu - (optional) is a type of number
          cpu = ahv_config.value["cpu"]
          # disk_mib - (optional) is a type of number
          disk_mib = ahv_config.value["disk_mib"]
          # memory_mib - (optional) is a type of number
          memory_mib = ahv_config.value["memory_mib"]
          # network_uuid - (required) is a type of string
          network_uuid = ahv_config.value["network_uuid"]
          # prism_element_cluster_uuid - (required) is a type of string
          prism_element_cluster_uuid = ahv_config.value["prism_element_cluster_uuid"]
        }
      }

    }
  }

  dynamic "private_registry" {
    for_each = var.private_registry
    content {
      # registry_name - (required) is a type of string
      registry_name = private_registry.value["registry_name"]
    }
  }

  dynamic "single_master_config" {
    for_each = var.single_master_config
    content {
    }
  }

  dynamic "storage_class_config" {
    for_each = var.storage_class_config
    content {
      # name - (optional) is a type of string
      name = storage_class_config.value["name"]
      # reclaim_policy - (optional) is a type of string
      reclaim_policy = storage_class_config.value["reclaim_policy"]

      dynamic "volumes_config" {
        for_each = storage_class_config.value.volumes_config
        content {
          # file_system - (optional) is a type of string
          file_system = volumes_config.value["file_system"]
          # flash_mode - (optional) is a type of bool
          flash_mode = volumes_config.value["flash_mode"]
          # password - (required) is a type of string
          password = volumes_config.value["password"]
          # prism_element_cluster_uuid - (required) is a type of string
          prism_element_cluster_uuid = volumes_config.value["prism_element_cluster_uuid"]
          # storage_container - (required) is a type of string
          storage_container = volumes_config.value["storage_container"]
          # username - (required) is a type of string
          username = volumes_config.value["username"]
        }
      }

    }
  }

  dynamic "worker_node_pool" {
    for_each = var.worker_node_pool
    content {
      # name - (optional) is a type of string
      name = worker_node_pool.value["name"]
      # node_os_version - (required) is a type of string
      node_os_version = worker_node_pool.value["node_os_version"]
      # num_instances - (required) is a type of number
      num_instances = worker_node_pool.value["num_instances"]

      dynamic "ahv_config" {
        for_each = worker_node_pool.value.ahv_config
        content {
          # cpu - (optional) is a type of number
          cpu = ahv_config.value["cpu"]
          # disk_mib - (optional) is a type of number
          disk_mib = ahv_config.value["disk_mib"]
          # memory_mib - (optional) is a type of number
          memory_mib = ahv_config.value["memory_mib"]
          # network_uuid - (required) is a type of string
          network_uuid = ahv_config.value["network_uuid"]
          # prism_element_cluster_uuid - (required) is a type of string
          prism_element_cluster_uuid = ahv_config.value["prism_element_cluster_uuid"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "deployment_type" {
  description = "returns a string"
  value       = nutanix_karbon_cluster.this.deployment_type
}

output "id" {
  description = "returns a string"
  value       = nutanix_karbon_cluster.this.id
}

output "kubeapi_server_ipv4_address" {
  description = "returns a string"
  value       = nutanix_karbon_cluster.this.kubeapi_server_ipv4_address
}

output "status" {
  description = "returns a string"
  value       = nutanix_karbon_cluster.this.status
}

output "this" {
  value = nutanix_karbon_cluster.this
}
```

[top](#index)