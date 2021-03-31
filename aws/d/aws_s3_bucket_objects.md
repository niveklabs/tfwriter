# aws_s3_bucket_objects

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_s3_bucket_objects" {
  source = "./modules/aws/d/aws_s3_bucket_objects"

  # bucket - (required) is a type of string
  bucket = null
  # delimiter - (optional) is a type of string
  delimiter = null
  # encoding_type - (optional) is a type of string
  encoding_type = null
  # fetch_owner - (optional) is a type of bool
  fetch_owner = null
  # max_keys - (optional) is a type of number
  max_keys = null
  # prefix - (optional) is a type of string
  prefix = null
  # start_after - (optional) is a type of string
  start_after = null
}
```

[top](#index)

### Variables

```terraform
variable "bucket" {
  description = "(required)"
  type        = string
}

variable "delimiter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "encoding_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fetch_owner" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "max_keys" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "start_after" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aws_s3_bucket_objects" "this" {
  bucket        = var.bucket
  delimiter     = var.delimiter
  encoding_type = var.encoding_type
  fetch_owner   = var.fetch_owner
  max_keys      = var.max_keys
  prefix        = var.prefix
  start_after   = var.start_after
}
```

[top](#index)

### Outputs

```terraform
output "common_prefixes" {
  description = "returns a list of string"
  value       = data.aws_s3_bucket_objects.this.common_prefixes
}

output "id" {
  description = "returns a string"
  value       = data.aws_s3_bucket_objects.this.id
}

output "keys" {
  description = "returns a list of string"
  value       = data.aws_s3_bucket_objects.this.keys
}

output "owners" {
  description = "returns a list of string"
  value       = data.aws_s3_bucket_objects.this.owners
}

output "this" {
  value = aws_s3_bucket_objects.this
}
```

[top](#index)