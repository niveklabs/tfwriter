# ovh_cloud_project_kube

[back](../ovh.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ovh = ">= 0.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ovh_cloud_project_kube" {
  source = "./modules/ovh/r/ovh_cloud_project_kube"

  # name - (optional) is a type of string
  name = null
  # region - (required) is a type of string
  region = null
  # service_name - (required) is a type of string
  service_name = null
  # version - (optional) is a type of string
  version = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(required)"
  type        = string
}

variable "service_name" {
  description = "(required)"
  type        = string
}

variable "version" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "ovh_cloud_project_kube" "this" {
  # name - (optional) is a type of string
  name = var.name
  # region - (required) is a type of string
  region = var.region
  # service_name - (required) is a type of string
  service_name = var.service_name
  # version - (optional) is a type of string
  version = var.version
}
```

[top](#index)

### Outputs

```terraform
output "control_plane_is_up_to_date" {
  description = "returns a bool"
  value       = ovh_cloud_project_kube.this.control_plane_is_up_to_date
}

output "id" {
  description = "returns a string"
  value       = ovh_cloud_project_kube.this.id
}

output "is_up_to_date" {
  description = "returns a bool"
  value       = ovh_cloud_project_kube.this.is_up_to_date
}

output "kubeconfig" {
  description = "returns a string"
  value       = ovh_cloud_project_kube.this.kubeconfig
  sensitive   = true
}

output "next_upgrade_versions" {
  description = "returns a set of string"
  value       = ovh_cloud_project_kube.this.next_upgrade_versions
}

output "nodes_url" {
  description = "returns a string"
  value       = ovh_cloud_project_kube.this.nodes_url
}

output "status" {
  description = "returns a string"
  value       = ovh_cloud_project_kube.this.status
}

output "update_policy" {
  description = "returns a string"
  value       = ovh_cloud_project_kube.this.update_policy
}

output "url" {
  description = "returns a string"
  value       = ovh_cloud_project_kube.this.url
}

output "this" {
  value = ovh_cloud_project_kube.this
}
```

[top](#index)