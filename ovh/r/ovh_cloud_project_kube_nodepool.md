# ovh_cloud_project_kube_nodepool

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
module "ovh_cloud_project_kube_nodepool" {
  source = "./modules/ovh/r/ovh_cloud_project_kube_nodepool"

  # anti_affinity - (optional) is a type of bool
  anti_affinity = null
  # desired_nodes - (optional) is a type of number
  desired_nodes = null
  # flavor_name - (required) is a type of string
  flavor_name = null
  # kube_id - (required) is a type of string
  kube_id = null
  # max_nodes - (optional) is a type of number
  max_nodes = null
  # min_nodes - (optional) is a type of number
  min_nodes = null
  # monthly_billed - (optional) is a type of bool
  monthly_billed = null
  # name - (optional) is a type of string
  name = null
  # service_name - (required) is a type of string
  service_name = null
}
```

[top](#index)

### Variables

```terraform
variable "anti_affinity" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "desired_nodes" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "flavor_name" {
  description = "(required)"
  type        = string
}

variable "kube_id" {
  description = "(required)"
  type        = string
}

variable "max_nodes" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "min_nodes" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "monthly_billed" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "ovh_cloud_project_kube_nodepool" "this" {
  # anti_affinity - (optional) is a type of bool
  anti_affinity = var.anti_affinity
  # desired_nodes - (optional) is a type of number
  desired_nodes = var.desired_nodes
  # flavor_name - (required) is a type of string
  flavor_name = var.flavor_name
  # kube_id - (required) is a type of string
  kube_id = var.kube_id
  # max_nodes - (optional) is a type of number
  max_nodes = var.max_nodes
  # min_nodes - (optional) is a type of number
  min_nodes = var.min_nodes
  # monthly_billed - (optional) is a type of bool
  monthly_billed = var.monthly_billed
  # name - (optional) is a type of string
  name = var.name
  # service_name - (required) is a type of string
  service_name = var.service_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = ovh_cloud_project_kube_nodepool.this.id
}

output "status" {
  description = "returns a string"
  value       = ovh_cloud_project_kube_nodepool.this.status
}

output "this" {
  value = ovh_cloud_project_kube_nodepool.this
}
```

[top](#index)