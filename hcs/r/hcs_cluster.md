# hcs_cluster

[back](../hcs.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
  source = "./modules/hcs/r/hcs_cluster"

  # cluster_mode - (required) is a type of string
  cluster_mode = null
  # cluster_name - (optional) is a type of string
  cluster_name = null
  # consul_datacenter - (optional) is a type of string
  consul_datacenter = null
  # consul_external_endpoint - (optional) is a type of bool
  consul_external_endpoint = null
  # consul_federation_token - (optional) is a type of string
  consul_federation_token = null
  # email - (required) is a type of string
  email = null
  # location - (optional) is a type of string
  location = null
  # managed_application_name - (required) is a type of string
  managed_application_name = null
  # managed_resource_group_name - (optional) is a type of string
  managed_resource_group_name = null
  # min_consul_version - (optional) is a type of string
  min_consul_version = null
  # plan_name - (optional) is a type of string
  plan_name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vnet_cidr - (optional) is a type of string
  vnet_cidr = null

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
variable "cluster_mode" {
  description = "(required) - The mode of the cluster ('Development' or 'Production'). Development clusters only have a single Consul server. Production clusters are fully supported, full featured, and deploy with a minimum of three hosts."
  type        = string
}

variable "cluster_name" {
  description = "(optional) - The name of the cluster Managed Resource. If not specified, it is defaulted to the value of `managed_application_name`."
  type        = string
  default     = null
}

variable "consul_datacenter" {
  description = "(optional) - The Consul data center name of the cluster. If not specified, it is defaulted to the value of `managed_application_name`."
  type        = string
  default     = null
}

variable "consul_external_endpoint" {
  description = "(optional) - Denotes that the cluster has an external endpoint for the Consul UI. Defaults to `false`."
  type        = bool
  default     = null
}

variable "consul_federation_token" {
  description = "(optional) - The token used to join a federation of Consul clusters. If the cluster is not part of a federation, this field will be empty."
  type        = string
  default     = null
}

variable "email" {
  description = "(required) - The contact email for the primary owner of the cluster."
  type        = string
}

variable "location" {
  description = "(optional) - The Azure region that the cluster is deployed to. If not specified, it is defaulted to the region of the Resource Group the Managed Application belongs to."
  type        = string
  default     = null
}

variable "managed_application_name" {
  description = "(required) - The name of the HCS Azure Managed Application."
  type        = string
}

variable "managed_resource_group_name" {
  description = "(optional) - The name of the Managed Resource Group in which the cluster resources belong. If not specified, it is defaulted to the value of `managed_application_name` with 'mrg-' prepended."
  type        = string
  default     = null
}

variable "min_consul_version" {
  description = "(optional) - The minimum Consul version of the cluster. If not specified, it is defaulted to the version that is currently recommended by HCS."
  type        = string
  default     = null
}

variable "plan_name" {
  description = "(optional) - The name of the Azure Marketplace HCS plan for the cluster. If not specified, it will default to the current HCS default plan (see the `hcs_plan_defaults` data source)."
  type        = string
  default     = null
}

variable "resource_group_name" {
  description = "(required) - The name of the Resource Group in which the HCS Azure Managed Application belongs."
  type        = string
}

variable "tags" {
  description = "(optional) - A mapping of tags to assign to the HCS Azure Managed Application resource."
  type        = map(string)
  default     = null
}

variable "vnet_cidr" {
  description = "(optional) - The VNET CIDR range of the Consul cluster. Defaults to `172.25.16.0/24`."
  type        = string
  default     = null
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
resource "hcs_cluster" "this" {
  # cluster_mode - (required) is a type of string
  cluster_mode = var.cluster_mode
  # cluster_name - (optional) is a type of string
  cluster_name = var.cluster_name
  # consul_datacenter - (optional) is a type of string
  consul_datacenter = var.consul_datacenter
  # consul_external_endpoint - (optional) is a type of bool
  consul_external_endpoint = var.consul_external_endpoint
  # consul_federation_token - (optional) is a type of string
  consul_federation_token = var.consul_federation_token
  # email - (required) is a type of string
  email = var.email
  # location - (optional) is a type of string
  location = var.location
  # managed_application_name - (required) is a type of string
  managed_application_name = var.managed_application_name
  # managed_resource_group_name - (optional) is a type of string
  managed_resource_group_name = var.managed_resource_group_name
  # min_consul_version - (optional) is a type of string
  min_consul_version = var.min_consul_version
  # plan_name - (optional) is a type of string
  plan_name = var.plan_name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # tags - (optional) is a type of map of string
  tags = var.tags
  # vnet_cidr - (optional) is a type of string
  vnet_cidr = var.vnet_cidr

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # default - (optional) is a type of string
      default = timeouts.value["default"]
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
output "blob_container_name" {
  description = "returns a string"
  value       = hcs_cluster.this.blob_container_name
}

output "cluster_name" {
  description = "returns a string"
  value       = hcs_cluster.this.cluster_name
}

output "consul_automatic_upgrades" {
  description = "returns a bool"
  value       = hcs_cluster.this.consul_automatic_upgrades
}

output "consul_ca_file" {
  description = "returns a string"
  value       = hcs_cluster.this.consul_ca_file
}

output "consul_cluster_id" {
  description = "returns a string"
  value       = hcs_cluster.this.consul_cluster_id
}

output "consul_config_file" {
  description = "returns a string"
  value       = hcs_cluster.this.consul_config_file
}

output "consul_connect" {
  description = "returns a bool"
  value       = hcs_cluster.this.consul_connect
}

output "consul_datacenter" {
  description = "returns a string"
  value       = hcs_cluster.this.consul_datacenter
}

output "consul_external_endpoint_url" {
  description = "returns a string"
  value       = hcs_cluster.this.consul_external_endpoint_url
}

output "consul_private_endpoint_url" {
  description = "returns a string"
  value       = hcs_cluster.this.consul_private_endpoint_url
}

output "consul_root_token_accessor_id" {
  description = "returns a string"
  value       = hcs_cluster.this.consul_root_token_accessor_id
}

output "consul_root_token_secret_id" {
  description = "returns a string"
  value       = hcs_cluster.this.consul_root_token_secret_id
  sensitive   = true
}

output "consul_snapshot_interval" {
  description = "returns a string"
  value       = hcs_cluster.this.consul_snapshot_interval
}

output "consul_snapshot_retention" {
  description = "returns a string"
  value       = hcs_cluster.this.consul_snapshot_retention
}

output "consul_version" {
  description = "returns a string"
  value       = hcs_cluster.this.consul_version
}

output "id" {
  description = "returns a string"
  value       = hcs_cluster.this.id
}

output "location" {
  description = "returns a string"
  value       = hcs_cluster.this.location
}

output "managed_application_id" {
  description = "returns a string"
  value       = hcs_cluster.this.managed_application_id
}

output "managed_resource_group_name" {
  description = "returns a string"
  value       = hcs_cluster.this.managed_resource_group_name
}

output "plan_name" {
  description = "returns a string"
  value       = hcs_cluster.this.plan_name
}

output "state" {
  description = "returns a string"
  value       = hcs_cluster.this.state
}

output "storage_account_name" {
  description = "returns a string"
  value       = hcs_cluster.this.storage_account_name
}

output "storage_account_resource_group" {
  description = "returns a string"
  value       = hcs_cluster.this.storage_account_resource_group
}

output "vnet_id" {
  description = "returns a string"
  value       = hcs_cluster.this.vnet_id
}

output "vnet_name" {
  description = "returns a string"
  value       = hcs_cluster.this.vnet_name
}

output "vnet_resource_group_name" {
  description = "returns a string"
  value       = hcs_cluster.this.vnet_resource_group_name
}

output "this" {
  value = hcs_cluster.this
}
```

[top](#index)