# mongodbatlas_encryption_at_rest

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
module "mongodbatlas_encryption_at_rest" {
  source = "./modules/mongodbatlas/r/mongodbatlas_encryption_at_rest"

  # aws_kms - (optional) is a type of map of string
  aws_kms = {}
  # azure_key_vault - (optional) is a type of map of string
  azure_key_vault = {}
  # google_cloud_kms - (optional) is a type of map of string
  google_cloud_kms = {}
  # project_id - (required) is a type of string
  project_id = null
}
```

[top](#index)

### Variables

```terraform
variable "aws_kms" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "azure_key_vault" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "google_cloud_kms" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "project_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "mongodbatlas_encryption_at_rest" "this" {
  aws_kms          = var.aws_kms
  azure_key_vault  = var.azure_key_vault
  google_cloud_kms = var.google_cloud_kms
  project_id       = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = mongodbatlas_encryption_at_rest.this.id
}

output "this" {
  value = mongodbatlas_encryption_at_rest.this
}
```

[top](#index)