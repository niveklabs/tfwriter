# rancher2_cluster_template

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
module "rancher2_cluster_template" {
  source = "./modules/rancher2/d/rancher2_cluster_template"

  # annotations - (optional) is a type of map of string
  annotations = {}
  # description - (optional) is a type of string
  description = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "annotations" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "description" {
  description = "(optional) - Cluster template description"
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - Cluster template name"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "rancher2_cluster_template" "this" {
  # annotations - (optional) is a type of map of string
  annotations = var.annotations
  # description - (optional) is a type of string
  description = var.description
  # labels - (optional) is a type of map of string
  labels = var.labels
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "annotations" {
  description = "returns a map of string"
  value       = data.rancher2_cluster_template.this.annotations
}

output "default_revision_id" {
  description = "returns a string"
  value       = data.rancher2_cluster_template.this.default_revision_id
}

output "description" {
  description = "returns a string"
  value       = data.rancher2_cluster_template.this.description
}

output "id" {
  description = "returns a string"
  value       = data.rancher2_cluster_template.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = data.rancher2_cluster_template.this.labels
}

output "members" {
  description = "returns a list of object"
  value       = data.rancher2_cluster_template.this.members
}

output "template_revisions" {
  description = "returns a list of object"
  value       = data.rancher2_cluster_template.this.template_revisions
}

output "this" {
  value = rancher2_cluster_template.this
}
```

[top](#index)