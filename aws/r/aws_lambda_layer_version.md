# aws_lambda_layer_version

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_lambda_layer_version" {
  source = "./modules/aws/r/aws_lambda_layer_version"

  # compatible_runtimes - (optional) is a type of set of string
  compatible_runtimes = []
  # description - (optional) is a type of string
  description = null
  # filename - (optional) is a type of string
  filename = null
  # layer_name - (required) is a type of string
  layer_name = null
  # license_info - (optional) is a type of string
  license_info = null
  # s3_bucket - (optional) is a type of string
  s3_bucket = null
  # s3_key - (optional) is a type of string
  s3_key = null
  # s3_object_version - (optional) is a type of string
  s3_object_version = null
  # source_code_hash - (optional) is a type of string
  source_code_hash = null
}
```

[top](#index)

### Variables

```terraform
variable "compatible_runtimes" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "filename" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "layer_name" {
  description = "(required)"
  type        = string
}

variable "license_info" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "s3_bucket" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "s3_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "s3_object_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_code_hash" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_lambda_layer_version" "this" {
  # compatible_runtimes - (optional) is a type of set of string
  compatible_runtimes = var.compatible_runtimes
  # description - (optional) is a type of string
  description = var.description
  # filename - (optional) is a type of string
  filename = var.filename
  # layer_name - (required) is a type of string
  layer_name = var.layer_name
  # license_info - (optional) is a type of string
  license_info = var.license_info
  # s3_bucket - (optional) is a type of string
  s3_bucket = var.s3_bucket
  # s3_key - (optional) is a type of string
  s3_key = var.s3_key
  # s3_object_version - (optional) is a type of string
  s3_object_version = var.s3_object_version
  # source_code_hash - (optional) is a type of string
  source_code_hash = var.source_code_hash
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_lambda_layer_version.this.arn
}

output "created_date" {
  description = "returns a string"
  value       = aws_lambda_layer_version.this.created_date
}

output "id" {
  description = "returns a string"
  value       = aws_lambda_layer_version.this.id
}

output "layer_arn" {
  description = "returns a string"
  value       = aws_lambda_layer_version.this.layer_arn
}

output "signing_job_arn" {
  description = "returns a string"
  value       = aws_lambda_layer_version.this.signing_job_arn
}

output "signing_profile_version_arn" {
  description = "returns a string"
  value       = aws_lambda_layer_version.this.signing_profile_version_arn
}

output "source_code_hash" {
  description = "returns a string"
  value       = aws_lambda_layer_version.this.source_code_hash
}

output "source_code_size" {
  description = "returns a number"
  value       = aws_lambda_layer_version.this.source_code_size
}

output "version" {
  description = "returns a string"
  value       = aws_lambda_layer_version.this.version
}

output "this" {
  value = aws_lambda_layer_version.this
}
```

[top](#index)