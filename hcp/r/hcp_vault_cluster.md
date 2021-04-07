# hcp_vault_cluster

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
    hcp = ">= 0.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "hcp_vault_cluster" {
  source = "./modules/hcp/r/hcp_vault_cluster"

  # cluster_id - (required) is a type of string
  cluster_id = null
  # hvn_id - (required) is a type of string
  hvn_id = null
  # min_vault_version - (optional) is a type of string
  min_vault_version = null
  # public_endpoint - (optional) is a type of bool
  public_endpoint = null

  timeouts = [{
    create  = null
    default = null
    delete  = null
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

variable "hvn_id" {
  description = "(required) - The ID of the HVN this HCP Vault cluster is associated to."
  type        = string
}

variable "min_vault_version" {
  description = "(optional) - The minimum Vault version to use when creating the cluster. If not specified, it is defaulted to the version that is currently recommended by HCP."
  type        = string
  default     = null
}

variable "public_endpoint" {
  description = "(optional) - Denotes that the cluster has a public endpoint. Defaults to false."
  type        = bool
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create  = string
      default = string
      delete  = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "hcp_vault_cluster" "this" {
  cluster_id        = var.cluster_id
  hvn_id            = var.hvn_id
  min_vault_version = var.min_vault_version
  public_endpoint   = var.public_endpoint

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create  = timeouts.value["create"]
      default = timeouts.value["default"]
      delete  = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cloud_provider" {
  description = "returns a string"
  value       = hcp_vault_cluster.this.cloud_provider
}

output "created_at" {
  description = "returns a string"
  value       = hcp_vault_cluster.this.created_at
}

output "id" {
  description = "returns a string"
  value       = hcp_vault_cluster.this.id
}

output "namespace" {
  description = "returns a string"
  value       = hcp_vault_cluster.this.namespace
}

output "organization_id" {
  description = "returns a string"
  value       = hcp_vault_cluster.this.organization_id
}

output "project_id" {
  description = "returns a string"
  value       = hcp_vault_cluster.this.project_id
}

output "region" {
  description = "returns a string"
  value       = hcp_vault_cluster.this.region
}

output "tier" {
  description = "returns a string"
  value       = hcp_vault_cluster.this.tier
}

output "vault_private_endpoint_url" {
  description = "returns a string"
  value       = hcp_vault_cluster.this.vault_private_endpoint_url
}

output "vault_public_endpoint_url" {
  description = "returns a string"
  value       = hcp_vault_cluster.this.vault_public_endpoint_url
}

output "vault_version" {
  description = "returns a string"
  value       = hcp_vault_cluster.this.vault_version
}

output "this" {
  value = hcp_vault_cluster.this
}
```

[top](#index)