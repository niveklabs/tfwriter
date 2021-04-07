# rancher2_secret

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
module "rancher2_secret" {
  source = "./modules/rancher2/d/rancher2_secret"

  # name - (required) is a type of string
  name = null
  # namespace_id - (optional) is a type of string
  namespace_id = null
  # project_id - (required) is a type of string
  project_id = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - Name of the secret"
  type        = string
}

variable "namespace_id" {
  description = "(optional) - Namespace ID to add secret"
  type        = string
  default     = null
}

variable "project_id" {
  description = "(required) - Project ID to add secret"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "rancher2_secret" "this" {
  # name - (required) is a type of string
  name = var.name
  # namespace_id - (optional) is a type of string
  namespace_id = var.namespace_id
  # project_id - (required) is a type of string
  project_id = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "annotations" {
  description = "returns a map of string"
  value       = data.rancher2_secret.this.annotations
}

output "data" {
  description = "returns a map of string"
  value       = data.rancher2_secret.this.data
}

output "description" {
  description = "returns a string"
  value       = data.rancher2_secret.this.description
}

output "id" {
  description = "returns a string"
  value       = data.rancher2_secret.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = data.rancher2_secret.this.labels
}

output "this" {
  value = rancher2_secret.this
}
```

[top](#index)