# hcp_consul_cluster

[back](../hcp.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    hcp = ">= 0.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "hcp_consul_cluster" {
  source = "./modules/hcp/d/hcp_consul_cluster"

  # cluster_id - (required) is a type of string
  cluster_id = null

  timeouts = [{
    default = null
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
data "hcp_consul_cluster" "this" {
  cluster_id = var.cluster_id

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
output "cloud_provider" {
  description = "returns a string"
  value       = data.hcp_consul_cluster.this.cloud_provider
}

output "connect_enabled" {
  description = "returns a bool"
  value       = data.hcp_consul_cluster.this.connect_enabled
}

output "consul_automatic_upgrades" {
  description = "returns a bool"
  value       = data.hcp_consul_cluster.this.consul_automatic_upgrades
}

output "consul_ca_file" {
  description = "returns a string"
  value       = data.hcp_consul_cluster.this.consul_ca_file
}

output "consul_config_file" {
  description = "returns a string"
  value       = data.hcp_consul_cluster.this.consul_config_file
}

output "consul_private_endpoint_url" {
  description = "returns a string"
  value       = data.hcp_consul_cluster.this.consul_private_endpoint_url
}

output "consul_public_endpoint_url" {
  description = "returns a string"
  value       = data.hcp_consul_cluster.this.consul_public_endpoint_url
}

output "consul_snapshot_interval" {
  description = "returns a string"
  value       = data.hcp_consul_cluster.this.consul_snapshot_interval
}

output "consul_snapshot_retention" {
  description = "returns a string"
  value       = data.hcp_consul_cluster.this.consul_snapshot_retention
}

output "consul_version" {
  description = "returns a string"
  value       = data.hcp_consul_cluster.this.consul_version
}

output "datacenter" {
  description = "returns a string"
  value       = data.hcp_consul_cluster.this.datacenter
}

output "hvn_id" {
  description = "returns a string"
  value       = data.hcp_consul_cluster.this.hvn_id
}

output "id" {
  description = "returns a string"
  value       = data.hcp_consul_cluster.this.id
}

output "organization_id" {
  description = "returns a string"
  value       = data.hcp_consul_cluster.this.organization_id
}

output "primary_link" {
  description = "returns a string"
  value       = data.hcp_consul_cluster.this.primary_link
}

output "project_id" {
  description = "returns a string"
  value       = data.hcp_consul_cluster.this.project_id
}

output "public_endpoint" {
  description = "returns a bool"
  value       = data.hcp_consul_cluster.this.public_endpoint
}

output "region" {
  description = "returns a string"
  value       = data.hcp_consul_cluster.this.region
}

output "scale" {
  description = "returns a number"
  value       = data.hcp_consul_cluster.this.scale
}

output "self_link" {
  description = "returns a string"
  value       = data.hcp_consul_cluster.this.self_link
}

output "size" {
  description = "returns a string"
  value       = data.hcp_consul_cluster.this.size
}

output "tier" {
  description = "returns a string"
  value       = data.hcp_consul_cluster.this.tier
}

output "this" {
  value = hcp_consul_cluster.this
}
```

[top](#index)