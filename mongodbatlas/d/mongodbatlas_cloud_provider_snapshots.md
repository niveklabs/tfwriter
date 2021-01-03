# mongodbatlas_cloud_provider_snapshots

[back](../mongodbatlas.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    mongodbatlas = ">= 0.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "mongodbatlas_cloud_provider_snapshots" {
  source = "./modules/mongodbatlas/d/mongodbatlas_cloud_provider_snapshots"

  # cluster_name - (required) is a type of string
  cluster_name = null
  # items_per_page - (optional) is a type of number
  items_per_page = null
  # page_num - (optional) is a type of number
  page_num = null
  # project_id - (required) is a type of string
  project_id = null
}
```

[top](#index)

### Variables

```terraform
variable "cluster_name" {
  description = "(required)"
  type        = string
}

variable "items_per_page" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "page_num" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "project_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "mongodbatlas_cloud_provider_snapshots" "this" {
  cluster_name   = var.cluster_name
  items_per_page = var.items_per_page
  page_num       = var.page_num
  project_id     = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.mongodbatlas_cloud_provider_snapshots.this.id
}

output "results" {
  description = "returns a list of object"
  value       = data.mongodbatlas_cloud_provider_snapshots.this.results
}

output "total_count" {
  description = "returns a number"
  value       = data.mongodbatlas_cloud_provider_snapshots.this.total_count
}

output "this" {
  value = mongodbatlas_cloud_provider_snapshots.this
}
```

[top](#index)