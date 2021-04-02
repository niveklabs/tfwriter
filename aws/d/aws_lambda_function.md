# aws_lambda_function

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
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_lambda_function" {
  source = "./modules/aws/d/aws_lambda_function"

  # function_name - (required) is a type of string
  function_name = null
  # qualifier - (optional) is a type of string
  qualifier = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "function_name" {
  description = "(required)"
  type        = string
}

variable "qualifier" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aws_lambda_function" "this" {
  function_name = var.function_name
  qualifier     = var.qualifier
  tags          = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = data.aws_lambda_function.this.arn
}

output "code_signing_config_arn" {
  description = "returns a string"
  value       = data.aws_lambda_function.this.code_signing_config_arn
}

output "dead_letter_config" {
  description = "returns a list of object"
  value       = data.aws_lambda_function.this.dead_letter_config
}

output "description" {
  description = "returns a string"
  value       = data.aws_lambda_function.this.description
}

output "environment" {
  description = "returns a list of object"
  value       = data.aws_lambda_function.this.environment
}

output "file_system_config" {
  description = "returns a list of object"
  value       = data.aws_lambda_function.this.file_system_config
}

output "handler" {
  description = "returns a string"
  value       = data.aws_lambda_function.this.handler
}

output "id" {
  description = "returns a string"
  value       = data.aws_lambda_function.this.id
}

output "invoke_arn" {
  description = "returns a string"
  value       = data.aws_lambda_function.this.invoke_arn
}

output "kms_key_arn" {
  description = "returns a string"
  value       = data.aws_lambda_function.this.kms_key_arn
}

output "last_modified" {
  description = "returns a string"
  value       = data.aws_lambda_function.this.last_modified
}

output "layers" {
  description = "returns a list of string"
  value       = data.aws_lambda_function.this.layers
}

output "memory_size" {
  description = "returns a number"
  value       = data.aws_lambda_function.this.memory_size
}

output "qualified_arn" {
  description = "returns a string"
  value       = data.aws_lambda_function.this.qualified_arn
}

output "reserved_concurrent_executions" {
  description = "returns a number"
  value       = data.aws_lambda_function.this.reserved_concurrent_executions
}

output "role" {
  description = "returns a string"
  value       = data.aws_lambda_function.this.role
}

output "runtime" {
  description = "returns a string"
  value       = data.aws_lambda_function.this.runtime
}

output "signing_job_arn" {
  description = "returns a string"
  value       = data.aws_lambda_function.this.signing_job_arn
}

output "signing_profile_version_arn" {
  description = "returns a string"
  value       = data.aws_lambda_function.this.signing_profile_version_arn
}

output "source_code_hash" {
  description = "returns a string"
  value       = data.aws_lambda_function.this.source_code_hash
}

output "source_code_size" {
  description = "returns a number"
  value       = data.aws_lambda_function.this.source_code_size
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_lambda_function.this.tags
}

output "timeout" {
  description = "returns a number"
  value       = data.aws_lambda_function.this.timeout
}

output "tracing_config" {
  description = "returns a list of object"
  value       = data.aws_lambda_function.this.tracing_config
}

output "version" {
  description = "returns a string"
  value       = data.aws_lambda_function.this.version
}

output "vpc_config" {
  description = "returns a list of object"
  value       = data.aws_lambda_function.this.vpc_config
}

output "this" {
  value = aws_lambda_function.this
}
```

[top](#index)