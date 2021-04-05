# rancher2_cluster

[back](../rancher2.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    rancher2 = ">= 1.13.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "rancher2_cluster" {
  source = "./modules/rancher2/d/rancher2_cluster"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "rancher2_cluster" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "aks_config" {
  description = "returns a list of object"
  value       = data.rancher2_cluster.this.aks_config
}

output "annotations" {
  description = "returns a map of string"
  value       = data.rancher2_cluster.this.annotations
}

output "cluster_auth_endpoint" {
  description = "returns a list of object"
  value       = data.rancher2_cluster.this.cluster_auth_endpoint
}

output "cluster_monitoring_input" {
  description = "returns a list of object"
  value       = data.rancher2_cluster.this.cluster_monitoring_input
}

output "cluster_registration_token" {
  description = "returns a list of object"
  value       = data.rancher2_cluster.this.cluster_registration_token
}

output "cluster_template_answers" {
  description = "returns a list of object"
  value       = data.rancher2_cluster.this.cluster_template_answers
}

output "cluster_template_id" {
  description = "returns a string"
  value       = data.rancher2_cluster.this.cluster_template_id
}

output "cluster_template_questions" {
  description = "returns a list of object"
  value       = data.rancher2_cluster.this.cluster_template_questions
}

output "cluster_template_revision_id" {
  description = "returns a string"
  value       = data.rancher2_cluster.this.cluster_template_revision_id
}

output "default_pod_security_policy_template_id" {
  description = "returns a string"
  value       = data.rancher2_cluster.this.default_pod_security_policy_template_id
}

output "default_project_id" {
  description = "returns a string"
  value       = data.rancher2_cluster.this.default_project_id
}

output "description" {
  description = "returns a string"
  value       = data.rancher2_cluster.this.description
}

output "driver" {
  description = "returns a string"
  value       = data.rancher2_cluster.this.driver
}

output "eks_config" {
  description = "returns a list of object"
  value       = data.rancher2_cluster.this.eks_config
}

output "eks_config_v2" {
  description = "returns a list of object"
  value       = data.rancher2_cluster.this.eks_config_v2
}

output "enable_cluster_alerting" {
  description = "returns a bool"
  value       = data.rancher2_cluster.this.enable_cluster_alerting
}

output "enable_cluster_monitoring" {
  description = "returns a bool"
  value       = data.rancher2_cluster.this.enable_cluster_monitoring
}

output "enable_network_policy" {
  description = "returns a bool"
  value       = data.rancher2_cluster.this.enable_network_policy
}

output "gke_config" {
  description = "returns a list of object"
  value       = data.rancher2_cluster.this.gke_config
}

output "id" {
  description = "returns a string"
  value       = data.rancher2_cluster.this.id
}

output "k3s_config" {
  description = "returns a list of object"
  value       = data.rancher2_cluster.this.k3s_config
}

output "kube_config" {
  description = "returns a string"
  value       = data.rancher2_cluster.this.kube_config
}

output "labels" {
  description = "returns a map of string"
  value       = data.rancher2_cluster.this.labels
}

output "oke_config" {
  description = "returns a list of object"
  value       = data.rancher2_cluster.this.oke_config
}

output "rke_config" {
  description = "returns a list of object"
  value       = data.rancher2_cluster.this.rke_config
}

output "scheduled_cluster_scan" {
  description = "returns a list of object"
  value       = data.rancher2_cluster.this.scheduled_cluster_scan
}

output "system_project_id" {
  description = "returns a string"
  value       = data.rancher2_cluster.this.system_project_id
}

output "this" {
  value = rancher2_cluster.this
}
```

[top](#index)