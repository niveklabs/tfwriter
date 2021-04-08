# vmc_cluster

[back](../vmc.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vmc = ">= 1.5.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vmc_cluster" {
  source = "./modules/vmc/r/vmc_cluster"

  # edrs_policy_type - (optional) is a type of string
  edrs_policy_type = null
  # enable_edrs - (optional) is a type of bool
  enable_edrs = null
  # host_cpu_cores_count - (optional) is a type of number
  host_cpu_cores_count = null
  # host_instance_type - (optional) is a type of string
  host_instance_type = null
  # max_hosts - (optional) is a type of number
  max_hosts = null
  # min_hosts - (optional) is a type of number
  min_hosts = null
  # num_hosts - (required) is a type of number
  num_hosts = null
  # sddc_id - (required) is a type of string
  sddc_id = null
  # storage_capacity - (optional) is a type of string
  storage_capacity = null

  microsoft_licensing_config = [{
    mssql_licensing   = null
    windows_licensing = null
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
variable "edrs_policy_type" {
  description = "(optional) - The EDRS policy type. This can either be 'cost', 'performance', 'storage-scaleup' or 'rapid-scaleup'. Default : storage-scaleup. "
  type        = string
  default     = null
}

variable "enable_edrs" {
  description = "(optional) - True if EDRS is enabled"
  type        = bool
  default     = null
}

variable "host_cpu_cores_count" {
  description = "(optional) - Customize CPU cores on hosts in a cluster. Specify number of cores to be enabled on hosts in a cluster."
  type        = number
  default     = null
}

variable "host_instance_type" {
  description = "(optional) - The instance type for the esx hosts added to this cluster."
  type        = string
  default     = null
}

variable "max_hosts" {
  description = "(optional) - The maximum number of hosts that the cluster can scale out to."
  type        = number
  default     = null
}

variable "min_hosts" {
  description = "(optional) - The minimum number of hosts that the cluster can scale in to."
  type        = number
  default     = null
}

variable "num_hosts" {
  description = "(required) - The number of hosts."
  type        = number
}

variable "sddc_id" {
  description = "(required) - SDDC identifier"
  type        = string
}

variable "storage_capacity" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "microsoft_licensing_config" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      mssql_licensing   = string
      windows_licensing = string
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
resource "vmc_cluster" "this" {
  # edrs_policy_type - (optional) is a type of string
  edrs_policy_type = var.edrs_policy_type
  # enable_edrs - (optional) is a type of bool
  enable_edrs = var.enable_edrs
  # host_cpu_cores_count - (optional) is a type of number
  host_cpu_cores_count = var.host_cpu_cores_count
  # host_instance_type - (optional) is a type of string
  host_instance_type = var.host_instance_type
  # max_hosts - (optional) is a type of number
  max_hosts = var.max_hosts
  # min_hosts - (optional) is a type of number
  min_hosts = var.min_hosts
  # num_hosts - (required) is a type of number
  num_hosts = var.num_hosts
  # sddc_id - (required) is a type of string
  sddc_id = var.sddc_id
  # storage_capacity - (optional) is a type of string
  storage_capacity = var.storage_capacity

  dynamic "microsoft_licensing_config" {
    for_each = var.microsoft_licensing_config
    content {
      # mssql_licensing - (optional) is a type of string
      mssql_licensing = microsoft_licensing_config.value["mssql_licensing"]
      # windows_licensing - (optional) is a type of string
      windows_licensing = microsoft_licensing_config.value["windows_licensing"]
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
output "cluster_info" {
  description = "returns a map of string"
  value       = vmc_cluster.this.cluster_info
}

output "id" {
  description = "returns a string"
  value       = vmc_cluster.this.id
}

output "this" {
  value = vmc_cluster.this
}
```

[top](#index)