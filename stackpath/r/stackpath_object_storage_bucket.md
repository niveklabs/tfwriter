# stackpath_object_storage_bucket

[back](../stackpath.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    stackpath = ">= 1.3.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "stackpath_object_storage_bucket" {
  source = "./modules/stackpath/r/stackpath_object_storage_bucket"

  # label - (required) is a type of string
  label = null
  # region - (required) is a type of string
  region = null
  # visibility - (optional) is a type of string
  visibility = null
}
```

[top](#index)

### Variables

```terraform
variable "label" {
  description = "(required)"
  type        = string
}

variable "region" {
  description = "(required)"
  type        = string
}

variable "visibility" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "stackpath_object_storage_bucket" "this" {
  # label - (required) is a type of string
  label = var.label
  # region - (required) is a type of string
  region = var.region
  # visibility - (optional) is a type of string
  visibility = var.visibility
}
```

[top](#index)

### Outputs

```terraform
output "endpoint_url" {
  description = "returns a string"
  value       = stackpath_object_storage_bucket.this.endpoint_url
}

output "id" {
  description = "returns a string"
  value       = stackpath_object_storage_bucket.this.id
}

output "this" {
  value = stackpath_object_storage_bucket.this
}
```

[top](#index)