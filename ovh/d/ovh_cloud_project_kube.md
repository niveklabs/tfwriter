# ovh_cloud_project_kube

[back](../ovh.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/ovh/d/ovh_cloud_project_kube"

  # kube_id - (required) is a type of string
  kube_id = null
  # name - (optional) is a type of string
  name = null
  # region - (optional) is a type of string
  region = null
  # service_name - (required) is a type of string
  service_name = null
  # update_policy - (optional) is a type of string
  update_policy = null
  # version - (optional) is a type of string
  version = null
}
```

[top](#index)

### Variables

```terraform
variable "kube_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_name" {
  description = "(required)"
  type        = string
}

variable "update_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "version" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "ovh_cloud_project_kube" "this" {
  kube_id       = var.kube_id
  name          = var.name
  region        = var.region
  service_name  = var.service_name
  update_policy = var.update_policy
  version       = var.version
}
```

[top](#index)

### Outputs

```terraform
output "control_plane_is_up_to_date" {
  description = "returns a bool"
  value       = data.ovh_cloud_project_kube.this.control_plane_is_up_to_date
}

output "id" {
  description = "returns a string"
  value       = data.ovh_cloud_project_kube.this.id
}

output "is_up_to_date" {
  description = "returns a bool"
  value       = data.ovh_cloud_project_kube.this.is_up_to_date
}

output "next_upgrade_versions" {
  description = "returns a set of string"
  value       = data.ovh_cloud_project_kube.this.next_upgrade_versions
}

output "nodes_url" {
  description = "returns a string"
  value       = data.ovh_cloud_project_kube.this.nodes_url
}

output "status" {
  description = "returns a string"
  value       = data.ovh_cloud_project_kube.this.status
}

output "url" {
  description = "returns a string"
  value       = data.ovh_cloud_project_kube.this.url
}

output "this" {
  value = ovh_cloud_project_kube.this
}
```

[top](#index)