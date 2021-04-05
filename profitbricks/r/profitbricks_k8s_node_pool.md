# profitbricks_k8s_node_pool

[back](../profitbricks.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    profitbricks = ">= 1.6.5"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "profitbricks_k8s_node_pool" {
  source = "./modules/profitbricks/r/profitbricks_k8s_node_pool"

  # availability_zone - (required) is a type of string
  availability_zone = null
  # cores_count - (required) is a type of number
  cores_count = null
  # cpu_family - (required) is a type of string
  cpu_family = null
  # datacenter_id - (required) is a type of string
  datacenter_id = null
  # k8s_cluster_id - (required) is a type of string
  k8s_cluster_id = null
  # k8s_version - (required) is a type of string
  k8s_version = null
  # lans - (optional) is a type of list of number
  lans = []
  # name - (required) is a type of string
  name = null
  # node_count - (required) is a type of number
  node_count = null
  # public_ips - (optional) is a type of list of string
  public_ips = []
  # ram_size - (required) is a type of number
  ram_size = null
  # storage_size - (required) is a type of number
  storage_size = null
  # storage_type - (required) is a type of string
  storage_type = null

  auto_scaling = [{
    max_node_count = null
    min_node_count = null
  }]

  maintenance_window = [{
    day_of_the_week = null
    time            = null
  }]

  timeouts = [{
    create  = null
    default = null
    delete  = null
    update  = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "availability_zone" {
  description = "(required) - The compute availability zone in which the nodes should exist"
  type        = string
}

variable "cores_count" {
  description = "(required) - CPU cores count"
  type        = number
}

variable "cpu_family" {
  description = "(required) - CPU Family"
  type        = string
}

variable "datacenter_id" {
  description = "(required) - The UUID of the VDC"
  type        = string
}

variable "k8s_cluster_id" {
  description = "(required) - The UUID of an existing kubernetes cluster"
  type        = string
}

variable "k8s_version" {
  description = "(required) - The desired kubernetes version"
  type        = string
}

variable "lans" {
  description = "(optional) - A list of Local Area Networks the node pool should be part of"
  type        = list(number)
  default     = null
}

variable "name" {
  description = "(required) - The desired name for the node pool"
  type        = string
}

variable "node_count" {
  description = "(required) - The number of nodes in this node pool"
  type        = number
}

variable "public_ips" {
  description = "(optional) - A list of fixed IPs"
  type        = list(string)
  default     = null
}

variable "ram_size" {
  description = "(required) - The amount of RAM in MB"
  type        = number
}

variable "storage_size" {
  description = "(required) - The total allocated storage capacity of a node in GB"
  type        = number
}

variable "storage_type" {
  description = "(required) - Storage type to use"
  type        = string
}

variable "auto_scaling" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      max_node_count = number
      min_node_count = number
    }
  ))
  default = []
}

variable "maintenance_window" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      day_of_the_week = string
      time            = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create  = string
      default = string
      delete  = string
      update  = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "profitbricks_k8s_node_pool" "this" {
  availability_zone = var.availability_zone
  cores_count       = var.cores_count
  cpu_family        = var.cpu_family
  datacenter_id     = var.datacenter_id
  k8s_cluster_id    = var.k8s_cluster_id
  k8s_version       = var.k8s_version
  lans              = var.lans
  name              = var.name
  node_count        = var.node_count
  public_ips        = var.public_ips
  ram_size          = var.ram_size
  storage_size      = var.storage_size
  storage_type      = var.storage_type

  dynamic "auto_scaling" {
    for_each = var.auto_scaling
    content {
      max_node_count = auto_scaling.value["max_node_count"]
      min_node_count = auto_scaling.value["min_node_count"]
    }
  }

  dynamic "maintenance_window" {
    for_each = var.maintenance_window
    content {
      day_of_the_week = maintenance_window.value["day_of_the_week"]
      time            = maintenance_window.value["time"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create  = timeouts.value["create"]
      default = timeouts.value["default"]
      delete  = timeouts.value["delete"]
      update  = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = profitbricks_k8s_node_pool.this.id
}

output "this" {
  value = profitbricks_k8s_node_pool.this
}
```

[top](#index)