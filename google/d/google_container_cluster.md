# google_container_cluster

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google = ">= 3.62.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_container_cluster" {
  source = "./modules/google/d/google_container_cluster"

  # location - (optional) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
}
```

[top](#index)

### Variables

```terraform
variable "location" {
  description = "(optional) - The location (region or zone) in which the cluster master will be created, as well as the default node location. If you specify a zone (such as us-central1-a), the cluster will be a zonal cluster with a single cluster master. If you specify a region (such as us-west1), the cluster will be a regional cluster with multiple masters spread across zones in the region, and with default node locations in those zones as well."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - The name of the cluster, unique within the project and location."
  type        = string
}

variable "project" {
  description = "(optional) - The ID of the project in which the resource belongs. If it is not provided, the provider project is used."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "google_container_cluster" "this" {
  location = var.location
  name     = var.name
  project  = var.project
}
```

[top](#index)

### Outputs

```terraform
output "addons_config" {
  description = "returns a list of object"
  value       = data.google_container_cluster.this.addons_config
}

output "authenticator_groups_config" {
  description = "returns a list of object"
  value       = data.google_container_cluster.this.authenticator_groups_config
}

output "cluster_autoscaling" {
  description = "returns a list of object"
  value       = data.google_container_cluster.this.cluster_autoscaling
}

output "cluster_ipv4_cidr" {
  description = "returns a string"
  value       = data.google_container_cluster.this.cluster_ipv4_cidr
}

output "database_encryption" {
  description = "returns a list of object"
  value       = data.google_container_cluster.this.database_encryption
}

output "datapath_provider" {
  description = "returns a string"
  value       = data.google_container_cluster.this.datapath_provider
}

output "default_max_pods_per_node" {
  description = "returns a number"
  value       = data.google_container_cluster.this.default_max_pods_per_node
}

output "default_snat_status" {
  description = "returns a list of object"
  value       = data.google_container_cluster.this.default_snat_status
}

output "description" {
  description = "returns a string"
  value       = data.google_container_cluster.this.description
}

output "enable_binary_authorization" {
  description = "returns a bool"
  value       = data.google_container_cluster.this.enable_binary_authorization
}

output "enable_intranode_visibility" {
  description = "returns a bool"
  value       = data.google_container_cluster.this.enable_intranode_visibility
}

output "enable_kubernetes_alpha" {
  description = "returns a bool"
  value       = data.google_container_cluster.this.enable_kubernetes_alpha
}

output "enable_legacy_abac" {
  description = "returns a bool"
  value       = data.google_container_cluster.this.enable_legacy_abac
}

output "enable_shielded_nodes" {
  description = "returns a bool"
  value       = data.google_container_cluster.this.enable_shielded_nodes
}

output "enable_tpu" {
  description = "returns a bool"
  value       = data.google_container_cluster.this.enable_tpu
}

output "endpoint" {
  description = "returns a string"
  value       = data.google_container_cluster.this.endpoint
}

output "id" {
  description = "returns a string"
  value       = data.google_container_cluster.this.id
}

output "initial_node_count" {
  description = "returns a number"
  value       = data.google_container_cluster.this.initial_node_count
}

output "instance_group_urls" {
  description = "returns a list of string"
  value       = data.google_container_cluster.this.instance_group_urls
}

output "ip_allocation_policy" {
  description = "returns a list of object"
  value       = data.google_container_cluster.this.ip_allocation_policy
}

output "label_fingerprint" {
  description = "returns a string"
  value       = data.google_container_cluster.this.label_fingerprint
}

output "logging_service" {
  description = "returns a string"
  value       = data.google_container_cluster.this.logging_service
}

output "maintenance_policy" {
  description = "returns a list of object"
  value       = data.google_container_cluster.this.maintenance_policy
}

output "master_auth" {
  description = "returns a list of object"
  value       = data.google_container_cluster.this.master_auth
}

output "master_authorized_networks_config" {
  description = "returns a list of object"
  value       = data.google_container_cluster.this.master_authorized_networks_config
}

output "master_version" {
  description = "returns a string"
  value       = data.google_container_cluster.this.master_version
}

output "min_master_version" {
  description = "returns a string"
  value       = data.google_container_cluster.this.min_master_version
}

output "monitoring_service" {
  description = "returns a string"
  value       = data.google_container_cluster.this.monitoring_service
}

output "network" {
  description = "returns a string"
  value       = data.google_container_cluster.this.network
}

output "network_policy" {
  description = "returns a list of object"
  value       = data.google_container_cluster.this.network_policy
}

output "node_config" {
  description = "returns a list of object"
  value       = data.google_container_cluster.this.node_config
}

output "node_locations" {
  description = "returns a set of string"
  value       = data.google_container_cluster.this.node_locations
}

output "node_pool" {
  description = "returns a list of object"
  value       = data.google_container_cluster.this.node_pool
}

output "node_version" {
  description = "returns a string"
  value       = data.google_container_cluster.this.node_version
}

output "operation" {
  description = "returns a string"
  value       = data.google_container_cluster.this.operation
}

output "pod_security_policy_config" {
  description = "returns a list of object"
  value       = data.google_container_cluster.this.pod_security_policy_config
}

output "private_cluster_config" {
  description = "returns a list of object"
  value       = data.google_container_cluster.this.private_cluster_config
}

output "release_channel" {
  description = "returns a list of object"
  value       = data.google_container_cluster.this.release_channel
}

output "remove_default_node_pool" {
  description = "returns a bool"
  value       = data.google_container_cluster.this.remove_default_node_pool
}

output "resource_labels" {
  description = "returns a map of string"
  value       = data.google_container_cluster.this.resource_labels
}

output "resource_usage_export_config" {
  description = "returns a list of object"
  value       = data.google_container_cluster.this.resource_usage_export_config
}

output "self_link" {
  description = "returns a string"
  value       = data.google_container_cluster.this.self_link
}

output "services_ipv4_cidr" {
  description = "returns a string"
  value       = data.google_container_cluster.this.services_ipv4_cidr
}

output "subnetwork" {
  description = "returns a string"
  value       = data.google_container_cluster.this.subnetwork
}

output "tpu_ipv4_cidr_block" {
  description = "returns a string"
  value       = data.google_container_cluster.this.tpu_ipv4_cidr_block
}

output "vertical_pod_autoscaling" {
  description = "returns a list of object"
  value       = data.google_container_cluster.this.vertical_pod_autoscaling
}

output "workload_identity_config" {
  description = "returns a list of object"
  value       = data.google_container_cluster.this.workload_identity_config
}

output "this" {
  value = google_container_cluster.this
}
```

[top](#index)