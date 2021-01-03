# nutanix_host

[back](../nutanix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nutanix = ">= 1.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nutanix_host" {
  source = "./modules/nutanix/d/nutanix_host"

  # host_id - (required) is a type of string
  host_id = null

  categories = [{
    name  = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "host_id" {
  description = "(required)"
  type        = string
}

variable "categories" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name  = string
      value = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "nutanix_host" "this" {
  host_id = var.host_id

  dynamic "categories" {
    for_each = var.categories
    content {
      name  = categories.value["name"]
      value = categories.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "api_version" {
  description = "returns a string"
  value       = data.nutanix_host.this.api_version
}

output "block" {
  description = "returns a map of string"
  value       = data.nutanix_host.this.block
}

output "cluster_reference" {
  description = "returns a map of string"
  value       = data.nutanix_host.this.cluster_reference
}

output "controller_vm" {
  description = "returns a map of string"
  value       = data.nutanix_host.this.controller_vm
}

output "cpu_capacity_hz" {
  description = "returns a number"
  value       = data.nutanix_host.this.cpu_capacity_hz
}

output "cpu_model" {
  description = "returns a string"
  value       = data.nutanix_host.this.cpu_model
}

output "failover_cluster" {
  description = "returns a map of string"
  value       = data.nutanix_host.this.failover_cluster
}

output "gpu_driver_version" {
  description = "returns a string"
  value       = data.nutanix_host.this.gpu_driver_version
}

output "gpu_list" {
  description = "returns a list of object"
  value       = data.nutanix_host.this.gpu_list
}

output "host_disks_reference_list" {
  description = "returns a list of object"
  value       = data.nutanix_host.this.host_disks_reference_list
}

output "host_nics_id_list" {
  description = "returns a list of string"
  value       = data.nutanix_host.this.host_nics_id_list
}

output "host_type" {
  description = "returns a string"
  value       = data.nutanix_host.this.host_type
}

output "hypervisor" {
  description = "returns a map of string"
  value       = data.nutanix_host.this.hypervisor
}

output "id" {
  description = "returns a string"
  value       = data.nutanix_host.this.id
}

output "ipmi" {
  description = "returns a map of string"
  value       = data.nutanix_host.this.ipmi
}

output "memory_capacity_mib" {
  description = "returns a number"
  value       = data.nutanix_host.this.memory_capacity_mib
}

output "metadata" {
  description = "returns a map of string"
  value       = data.nutanix_host.this.metadata
}

output "monitoring_state" {
  description = "returns a string"
  value       = data.nutanix_host.this.monitoring_state
}

output "name" {
  description = "returns a string"
  value       = data.nutanix_host.this.name
}

output "num_cpu_cores" {
  description = "returns a number"
  value       = data.nutanix_host.this.num_cpu_cores
}

output "num_cpu_sockets" {
  description = "returns a number"
  value       = data.nutanix_host.this.num_cpu_sockets
}

output "owner_reference" {
  description = "returns a map of string"
  value       = data.nutanix_host.this.owner_reference
}

output "project_reference" {
  description = "returns a map of string"
  value       = data.nutanix_host.this.project_reference
}

output "rackable_unit_reference" {
  description = "returns a map of string"
  value       = data.nutanix_host.this.rackable_unit_reference
}

output "serial_number" {
  description = "returns a string"
  value       = data.nutanix_host.this.serial_number
}

output "windows_domain" {
  description = "returns a map of string"
  value       = data.nutanix_host.this.windows_domain
}

output "this" {
  value = nutanix_host.this
}
```

[top](#index)