# mongodbatlas_projects

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
    mongodbatlas = ">= 0.8.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "mongodbatlas_projects" {
  source = "./modules/mongodbatlas/d/mongodbatlas_projects"

  # items_per_page - (optional) is a type of number
  items_per_page = null
  # page_num - (optional) is a type of number
  page_num = null
}
```

[top](#index)

### Variables

```terraform
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
```

[top](#index)

### Datasource

```terraform
data "mongodbatlas_projects" "this" {
  items_per_page = var.items_per_page
  page_num       = var.page_num
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.mongodbatlas_projects.this.id
}

output "results" {
  description = "returns a list of object"
  value       = data.mongodbatlas_projects.this.results
}

output "total_count" {
  description = "returns a number"
  value       = data.mongodbatlas_projects.this.total_count
}

output "this" {
  value = mongodbatlas_projects.this
}
```

[top](#index)