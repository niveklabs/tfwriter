# aws_lambda_layer_version

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
module "aws_lambda_layer_version" {
  source = "./modules/aws/d/aws_lambda_layer_version"

  # compatible_runtime - (optional) is a type of string
  compatible_runtime = null
  # layer_name - (required) is a type of string
  layer_name = null
  # version - (optional) is a type of number
  version = null
}
```

[top](#index)

### Variables

```terraform
variable "compatible_runtime" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "layer_name" {
  description = "(required)"
  type        = string
}

variable "version" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aws_lambda_layer_version" "this" {
  compatible_runtime = var.compatible_runtime
  layer_name         = var.layer_name
  version            = var.version
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = data.aws_lambda_layer_version.this.arn
}

output "compatible_runtimes" {
  description = "returns a set of string"
  value       = data.aws_lambda_layer_version.this.compatible_runtimes
}

output "created_date" {
  description = "returns a string"
  value       = data.aws_lambda_layer_version.this.created_date
}

output "description" {
  description = "returns a string"
  value       = data.aws_lambda_layer_version.this.description
}

output "id" {
  description = "returns a string"
  value       = data.aws_lambda_layer_version.this.id
}

output "layer_arn" {
  description = "returns a string"
  value       = data.aws_lambda_layer_version.this.layer_arn
}

output "license_info" {
  description = "returns a string"
  value       = data.aws_lambda_layer_version.this.license_info
}

output "signing_job_arn" {
  description = "returns a string"
  value       = data.aws_lambda_layer_version.this.signing_job_arn
}

output "signing_profile_version_arn" {
  description = "returns a string"
  value       = data.aws_lambda_layer_version.this.signing_profile_version_arn
}

output "source_code_hash" {
  description = "returns a string"
  value       = data.aws_lambda_layer_version.this.source_code_hash
}

output "source_code_size" {
  description = "returns a number"
  value       = data.aws_lambda_layer_version.this.source_code_size
}

output "version" {
  description = "returns a number"
  value       = data.aws_lambda_layer_version.this.version
}

output "this" {
  value = aws_lambda_layer_version.this
}
```

[top](#index)