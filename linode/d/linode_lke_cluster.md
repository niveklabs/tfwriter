# linode_lke_cluster

[back](../linode.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    linode = ">= 1.16.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "linode_lke_cluster" {
  source = "./modules/linode/d/linode_lke_cluster"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "linode_lke_cluster" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "api_endpoints" {
  description = "returns a list of string"
  value       = data.linode_lke_cluster.this.api_endpoints
}

output "id" {
  description = "returns a number"
  value       = data.linode_lke_cluster.this.id
}

output "k8s_version" {
  description = "returns a string"
  value       = data.linode_lke_cluster.this.k8s_version
}

output "kubeconfig" {
  description = "returns a string"
  value       = data.linode_lke_cluster.this.kubeconfig
  sensitive   = true
}

output "label" {
  description = "returns a string"
  value       = data.linode_lke_cluster.this.label
}

output "pools" {
  description = "returns a list of object"
  value       = data.linode_lke_cluster.this.pools
}

output "region" {
  description = "returns a string"
  value       = data.linode_lke_cluster.this.region
}

output "status" {
  description = "returns a string"
  value       = data.linode_lke_cluster.this.status
}

output "tags" {
  description = "returns a set of string"
  value       = data.linode_lke_cluster.this.tags
}

output "this" {
  value = linode_lke_cluster.this
}
```

[top](#index)