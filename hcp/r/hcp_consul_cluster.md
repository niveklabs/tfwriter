# hcp_consul_cluster

[back](../hcp.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    hcp = ">= 0.3.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "hcp_consul_cluster" {
  source = "./modules/hcp/r/hcp_consul_cluster"

  # cluster_id - (required) is a type of string
  cluster_id = null
  # connect_enabled - (optional) is a type of bool
  connect_enabled = null
  # datacenter - (optional) is a type of string
  datacenter = null
  # hvn_id - (required) is a type of string
  hvn_id = null
  # min_consul_version - (optional) is a type of string
  min_consul_version = null
  # primary_link - (optional) is a type of string
  primary_link = null
  # public_endpoint - (optional) is a type of bool
  public_endpoint = null
  # tier - (required) is a type of string
  tier = null

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
variable "cluster_id" {
  description = "(required) - The ID of the HCP Consul cluster."
  type        = string
}

variable "connect_enabled" {
  description = "(optional) - Denotes the Consul connect feature should be enabled for this cluster.  Default to true."
  type        = bool
  default     = null
}

variable "datacenter" {
  description = "(optional) - The Consul data center name of the cluster. If not specified, it is defaulted to the value of `cluster_id`."
  type        = string
  default     = null
}

variable "hvn_id" {
  description = "(required) - The ID of the HVN this HCP Consul cluster is associated to."
  type        = string
}

variable "min_consul_version" {
  description = "(optional) - The minimum Consul version of the cluster. If not specified, it is defaulted to the version that is currently recommended by HCP."
  type        = string
  default     = null
}

variable "primary_link" {
  description = "(optional) - The `self_link` of the HCP Consul cluster which is the primary in the federation setup with this HCP Consul cluster. If not specified, it is a standalone cluster."
  type        = string
  default     = null
}

variable "public_endpoint" {
  description = "(optional) - Denotes that the cluster has a public endpoint for the Consul UI. Defaults to false."
  type        = bool
  default     = null
}

variable "tier" {
  description = "(required) - The tier that the HCP Consul cluster will be provisioned as.  Only 'development' and 'standard' are available at this time."
  type        = string
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
resource "hcp_consul_cluster" "this" {
  cluster_id         = var.cluster_id
  connect_enabled    = var.connect_enabled
  datacenter         = var.datacenter
  hvn_id             = var.hvn_id
  min_consul_version = var.min_consul_version
  primary_link       = var.primary_link
  public_endpoint    = var.public_endpoint
  tier               = var.tier

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
output "cloud_provider" {
  description = "returns a string"
  value       = hcp_consul_cluster.this.cloud_provider
}

output "consul_automatic_upgrades" {
  description = "returns a bool"
  value       = hcp_consul_cluster.this.consul_automatic_upgrades
}

output "consul_ca_file" {
  description = "returns a string"
  value       = hcp_consul_cluster.this.consul_ca_file
}

output "consul_config_file" {
  description = "returns a string"
  value       = hcp_consul_cluster.this.consul_config_file
}

output "consul_private_endpoint_url" {
  description = "returns a string"
  value       = hcp_consul_cluster.this.consul_private_endpoint_url
}

output "consul_public_endpoint_url" {
  description = "returns a string"
  value       = hcp_consul_cluster.this.consul_public_endpoint_url
}

output "consul_root_token_accessor_id" {
  description = "returns a string"
  value       = hcp_consul_cluster.this.consul_root_token_accessor_id
}

output "consul_root_token_secret_id" {
  description = "returns a string"
  value       = hcp_consul_cluster.this.consul_root_token_secret_id
  sensitive   = true
}

output "consul_snapshot_interval" {
  description = "returns a string"
  value       = hcp_consul_cluster.this.consul_snapshot_interval
}

output "consul_snapshot_retention" {
  description = "returns a string"
  value       = hcp_consul_cluster.this.consul_snapshot_retention
}

output "consul_version" {
  description = "returns a string"
  value       = hcp_consul_cluster.this.consul_version
}

output "datacenter" {
  description = "returns a string"
  value       = hcp_consul_cluster.this.datacenter
}

output "id" {
  description = "returns a string"
  value       = hcp_consul_cluster.this.id
}

output "organization_id" {
  description = "returns a string"
  value       = hcp_consul_cluster.this.organization_id
}

output "project_id" {
  description = "returns a string"
  value       = hcp_consul_cluster.this.project_id
}

output "region" {
  description = "returns a string"
  value       = hcp_consul_cluster.this.region
}

output "scale" {
  description = "returns a number"
  value       = hcp_consul_cluster.this.scale
}

output "self_link" {
  description = "returns a string"
  value       = hcp_consul_cluster.this.self_link
}

output "this" {
  value = hcp_consul_cluster.this
}
```

[top](#index)