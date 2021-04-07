# tencentcloud_cos_bucket_object

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tencentcloud = ">= 1.56.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tencentcloud_cos_bucket_object" {
  source = "./modules/tencentcloud/d/tencentcloud_cos_bucket_object"

  # bucket - (required) is a type of string
  bucket = null
  # key - (required) is a type of string
  key = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "bucket" {
  description = "(required) - Name of the bucket that contains the objects to query."
  type        = string
}

variable "key" {
  description = "(required) - The full path to the object inside the bucket."
  type        = string
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_cos_bucket_object" "this" {
  bucket             = var.bucket
  key                = var.key
  result_output_file = var.result_output_file
}
```

[top](#index)

### Outputs

```terraform
output "cache_control" {
  description = "returns a string"
  value       = data.tencentcloud_cos_bucket_object.this.cache_control
}

output "content_disposition" {
  description = "returns a string"
  value       = data.tencentcloud_cos_bucket_object.this.content_disposition
}

output "content_encoding" {
  description = "returns a string"
  value       = data.tencentcloud_cos_bucket_object.this.content_encoding
}

output "content_type" {
  description = "returns a string"
  value       = data.tencentcloud_cos_bucket_object.this.content_type
}

output "etag" {
  description = "returns a string"
  value       = data.tencentcloud_cos_bucket_object.this.etag
}

output "id" {
  description = "returns a string"
  value       = data.tencentcloud_cos_bucket_object.this.id
}

output "last_modified" {
  description = "returns a string"
  value       = data.tencentcloud_cos_bucket_object.this.last_modified
}

output "storage_class" {
  description = "returns a string"
  value       = data.tencentcloud_cos_bucket_object.this.storage_class
}

output "this" {
  value = tencentcloud_cos_bucket_object.this
}
```

[top](#index)