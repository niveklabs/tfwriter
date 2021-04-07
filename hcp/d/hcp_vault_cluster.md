# hcp_vault_cluster

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
module "hcp_vault_cluster" {
  source = "./modules/hcp/d/hcp_vault_cluster"

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
  description = "(required) - The ID of the HCP Vault cluster."
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
data "hcp_vault_cluster" "this" {
  # cluster_id - (required) is a type of string
  cluster_id = var.cluster_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # default - (optional) is a type of string
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
  value       = data.hcp_vault_cluster.this.cloud_provider
}

output "created_at" {
  description = "returns a string"
  value       = data.hcp_vault_cluster.this.created_at
}

output "hvn_id" {
  description = "returns a string"
  value       = data.hcp_vault_cluster.this.hvn_id
}

output "id" {
  description = "returns a string"
  value       = data.hcp_vault_cluster.this.id
}

output "min_vault_version" {
  description = "returns a string"
  value       = data.hcp_vault_cluster.this.min_vault_version
}

output "namespace" {
  description = "returns a string"
  value       = data.hcp_vault_cluster.this.namespace
}

output "organization_id" {
  description = "returns a string"
  value       = data.hcp_vault_cluster.this.organization_id
}

output "project_id" {
  description = "returns a string"
  value       = data.hcp_vault_cluster.this.project_id
}

output "public_endpoint" {
  description = "returns a bool"
  value       = data.hcp_vault_cluster.this.public_endpoint
}

output "region" {
  description = "returns a string"
  value       = data.hcp_vault_cluster.this.region
}

output "tier" {
  description = "returns a string"
  value       = data.hcp_vault_cluster.this.tier
}

output "vault_private_endpoint_url" {
  description = "returns a string"
  value       = data.hcp_vault_cluster.this.vault_private_endpoint_url
}

output "vault_public_endpoint_url" {
  description = "returns a string"
  value       = data.hcp_vault_cluster.this.vault_public_endpoint_url
}

output "vault_version" {
  description = "returns a string"
  value       = data.hcp_vault_cluster.this.vault_version
}

output "this" {
  value = hcp_vault_cluster.this
}
```

[top](#index)