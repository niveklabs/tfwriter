# hcs_cluster

[back](../hcs.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    hcs = ">= 0.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "hcs_cluster" {
  source = "./modules/hcs/d/hcs_cluster"

  # cluster_name - (optional) is a type of string
  cluster_name = null
  # managed_application_name - (required) is a type of string
  managed_application_name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null

  timeouts = [{
    default = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cluster_name" {
  description = "(optional) - The name of the cluster Managed Resource. If not specified, it is defaulted to the value of `managed_application_name`."
  type        = string
  default     = null
}

variable "managed_application_name" {
  description = "(required) - The name of the HCS Azure Managed Application."
  type        = string
}

variable "resource_group_name" {
  description = "(required) - The name of the Resource Group in which the HCS Azure Managed Application belongs."
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      default = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "hcs_cluster" "this" {
  cluster_name             = var.cluster_name
  managed_application_name = var.managed_application_name
  resource_group_name      = var.resource_group_name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      default = timeouts.value["default"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "blob_container_name" {
  description = "returns a string"
  value       = data.hcs_cluster.this.blob_container_name
}

output "cluster_mode" {
  description = "returns a string"
  value       = data.hcs_cluster.this.cluster_mode
}

output "cluster_name" {
  description = "returns a string"
  value       = data.hcs_cluster.this.cluster_name
}

output "consul_automatic_upgrades" {
  description = "returns a bool"
  value       = data.hcs_cluster.this.consul_automatic_upgrades
}

output "consul_ca_file" {
  description = "returns a string"
  value       = data.hcs_cluster.this.consul_ca_file
}

output "consul_cluster_id" {
  description = "returns a string"
  value       = data.hcs_cluster.this.consul_cluster_id
}

output "consul_config_file" {
  description = "returns a string"
  value       = data.hcs_cluster.this.consul_config_file
}

output "consul_connect" {
  description = "returns a bool"
  value       = data.hcs_cluster.this.consul_connect
}

output "consul_datacenter" {
  description = "returns a string"
  value       = data.hcs_cluster.this.consul_datacenter
}

output "consul_external_endpoint" {
  description = "returns a bool"
  value       = data.hcs_cluster.this.consul_external_endpoint
}

output "consul_external_endpoint_url" {
  description = "returns a string"
  value       = data.hcs_cluster.this.consul_external_endpoint_url
}

output "consul_federation_token" {
  description = "returns a string"
  value       = data.hcs_cluster.this.consul_federation_token
}

output "consul_private_endpoint_url" {
  description = "returns a string"
  value       = data.hcs_cluster.this.consul_private_endpoint_url
}

output "consul_snapshot_interval" {
  description = "returns a string"
  value       = data.hcs_cluster.this.consul_snapshot_interval
}

output "consul_snapshot_retention" {
  description = "returns a string"
  value       = data.hcs_cluster.this.consul_snapshot_retention
}

output "consul_version" {
  description = "returns a string"
  value       = data.hcs_cluster.this.consul_version
}

output "email" {
  description = "returns a string"
  value       = data.hcs_cluster.this.email
}

output "id" {
  description = "returns a string"
  value       = data.hcs_cluster.this.id
}

output "location" {
  description = "returns a string"
  value       = data.hcs_cluster.this.location
}

output "managed_application_id" {
  description = "returns a string"
  value       = data.hcs_cluster.this.managed_application_id
}

output "managed_resource_group_name" {
  description = "returns a string"
  value       = data.hcs_cluster.this.managed_resource_group_name
}

output "plan_name" {
  description = "returns a string"
  value       = data.hcs_cluster.this.plan_name
}

output "state" {
  description = "returns a string"
  value       = data.hcs_cluster.this.state
}

output "storage_account_name" {
  description = "returns a string"
  value       = data.hcs_cluster.this.storage_account_name
}

output "storage_account_resource_group" {
  description = "returns a string"
  value       = data.hcs_cluster.this.storage_account_resource_group
}

output "tags" {
  description = "returns a map of string"
  value       = data.hcs_cluster.this.tags
}

output "vnet_cidr" {
  description = "returns a string"
  value       = data.hcs_cluster.this.vnet_cidr
}

output "vnet_id" {
  description = "returns a string"
  value       = data.hcs_cluster.this.vnet_id
}

output "vnet_name" {
  description = "returns a string"
  value       = data.hcs_cluster.this.vnet_name
}

output "vnet_resource_group_name" {
  description = "returns a string"
  value       = data.hcs_cluster.this.vnet_resource_group_name
}

output "this" {
  value = hcs_cluster.this
}
```

[top](#index)