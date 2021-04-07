# mongodbatlas_cloud_provider_access

[back](../mongodbatlas.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "mongodbatlas_cloud_provider_access" {
  source = "./modules/mongodbatlas/r/mongodbatlas_cloud_provider_access"

  # iam_assumed_role_arn - (optional) is a type of string
  iam_assumed_role_arn = null
  # project_id - (required) is a type of string
  project_id = null
  # provider_name - (required) is a type of string
  provider_name = null
}
```

[top](#index)

### Variables

```terraform
variable "iam_assumed_role_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "project_id" {
  description = "(required)"
  type        = string
}

variable "provider_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "mongodbatlas_cloud_provider_access" "this" {
  # iam_assumed_role_arn - (optional) is a type of string
  iam_assumed_role_arn = var.iam_assumed_role_arn
  # project_id - (required) is a type of string
  project_id = var.project_id
  # provider_name - (required) is a type of string
  provider_name = var.provider_name
}
```

[top](#index)

### Outputs

```terraform
output "atlas_assumed_role_external_id" {
  description = "returns a string"
  value       = mongodbatlas_cloud_provider_access.this.atlas_assumed_role_external_id
}

output "atlas_aws_account_arn" {
  description = "returns a string"
  value       = mongodbatlas_cloud_provider_access.this.atlas_aws_account_arn
}

output "authorized_date" {
  description = "returns a string"
  value       = mongodbatlas_cloud_provider_access.this.authorized_date
}

output "created_date" {
  description = "returns a string"
  value       = mongodbatlas_cloud_provider_access.this.created_date
}

output "feature_usages" {
  description = "returns a list of object"
  value       = mongodbatlas_cloud_provider_access.this.feature_usages
}

output "id" {
  description = "returns a string"
  value       = mongodbatlas_cloud_provider_access.this.id
}

output "role_id" {
  description = "returns a string"
  value       = mongodbatlas_cloud_provider_access.this.role_id
}

output "this" {
  value = mongodbatlas_cloud_provider_access.this
}
```

[top](#index)