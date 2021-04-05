# rancher2_project

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
module "rancher2_project" {
  source = "./modules/rancher2/d/rancher2_project"

  # cluster_id - (required) is a type of string
  cluster_id = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "cluster_id" {
  description = "(required) - ID of the cluster to whom the project belongs"
  type        = string
}

variable "name" {
  description = "(required) - Name of the project"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "rancher2_project" "this" {
  cluster_id = var.cluster_id
  name       = var.name
}
```

[top](#index)

### Outputs

```terraform
output "annotations" {
  description = "returns a map of string"
  value       = data.rancher2_project.this.annotations
}

output "container_resource_limit" {
  description = "returns a list of object"
  value       = data.rancher2_project.this.container_resource_limit
}

output "description" {
  description = "returns a string"
  value       = data.rancher2_project.this.description
}

output "enable_project_monitoring" {
  description = "returns a bool"
  value       = data.rancher2_project.this.enable_project_monitoring
}

output "id" {
  description = "returns a string"
  value       = data.rancher2_project.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = data.rancher2_project.this.labels
}

output "pod_security_policy_template_id" {
  description = "returns a string"
  value       = data.rancher2_project.this.pod_security_policy_template_id
}

output "resource_quota" {
  description = "returns a list of object"
  value       = data.rancher2_project.this.resource_quota
}

output "uuid" {
  description = "returns a string"
  value       = data.rancher2_project.this.uuid
}

output "this" {
  value = rancher2_project.this
}
```

[top](#index)