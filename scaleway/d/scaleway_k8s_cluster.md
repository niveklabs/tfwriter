# scaleway_k8s_cluster

[back](../scaleway.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    scaleway = ">= 2.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "scaleway_k8s_cluster" {
  source = "./modules/scaleway/d/scaleway_k8s_cluster"

  # cluster_id - (optional) is a type of string
  cluster_id = null
  # name - (optional) is a type of string
  name = null
  # region - (optional) is a type of string
  region = null
}
```

[top](#index)

### Variables

```terraform
variable "cluster_id" {
  description = "(optional) - The ID of the cluster"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - The name of the cluster"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - The region you want to attach the resource to"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "scaleway_k8s_cluster" "this" {
  # cluster_id - (optional) is a type of string
  cluster_id = var.cluster_id
  # name - (optional) is a type of string
  name = var.name
  # region - (optional) is a type of string
  region = var.region
}
```

[top](#index)

### Outputs

```terraform
output "admission_plugins" {
  description = "returns a list of string"
  value       = data.scaleway_k8s_cluster.this.admission_plugins
}

output "apiserver_cert_sans" {
  description = "returns a list of string"
  value       = data.scaleway_k8s_cluster.this.apiserver_cert_sans
}

output "apiserver_url" {
  description = "returns a string"
  value       = data.scaleway_k8s_cluster.this.apiserver_url
}

output "auto_upgrade" {
  description = "returns a list of object"
  value       = data.scaleway_k8s_cluster.this.auto_upgrade
}

output "autoscaler_config" {
  description = "returns a list of object"
  value       = data.scaleway_k8s_cluster.this.autoscaler_config
}

output "cni" {
  description = "returns a string"
  value       = data.scaleway_k8s_cluster.this.cni
}

output "created_at" {
  description = "returns a string"
  value       = data.scaleway_k8s_cluster.this.created_at
}

output "description" {
  description = "returns a string"
  value       = data.scaleway_k8s_cluster.this.description
}

output "feature_gates" {
  description = "returns a list of string"
  value       = data.scaleway_k8s_cluster.this.feature_gates
}

output "id" {
  description = "returns a string"
  value       = data.scaleway_k8s_cluster.this.id
}

output "kubeconfig" {
  description = "returns a list of object"
  value       = data.scaleway_k8s_cluster.this.kubeconfig
}

output "open_id_connect_config" {
  description = "returns a list of object"
  value       = data.scaleway_k8s_cluster.this.open_id_connect_config
}

output "organization_id" {
  description = "returns a string"
  value       = data.scaleway_k8s_cluster.this.organization_id
}

output "project_id" {
  description = "returns a string"
  value       = data.scaleway_k8s_cluster.this.project_id
}

output "status" {
  description = "returns a string"
  value       = data.scaleway_k8s_cluster.this.status
}

output "tags" {
  description = "returns a list of string"
  value       = data.scaleway_k8s_cluster.this.tags
}

output "updated_at" {
  description = "returns a string"
  value       = data.scaleway_k8s_cluster.this.updated_at
}

output "upgrade_available" {
  description = "returns a bool"
  value       = data.scaleway_k8s_cluster.this.upgrade_available
}

output "version" {
  description = "returns a string"
  value       = data.scaleway_k8s_cluster.this.version
}

output "wildcard_dns" {
  description = "returns a string"
  value       = data.scaleway_k8s_cluster.this.wildcard_dns
}

output "this" {
  value = scaleway_k8s_cluster.this
}
```

[top](#index)