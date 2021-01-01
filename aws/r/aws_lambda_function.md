# aws_lambda_function
[back](../aws.md)
### Index
- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)
### Terraform
```hcl
terraform {
  required_providers {
    aws = ">= 3.22.0"
  }
}
```
[top](#index)
### Example Usage
```hcl
module "aws_lambda_function" {
  source = "./modules/aws/r/aws_lambda_function"

  # code_signing_config_arn - (optional) is a type of string
  code_signing_config_arn = null
  # description - (optional) is a type of string
  description = null
  # filename - (optional) is a type of string
  filename = null
  # function_name - (required) is a type of string
  function_name = null
  # handler - (optional) is a type of string
  handler = null
  # image_uri - (optional) is a type of string
  image_uri = null
  # kms_key_arn - (optional) is a type of string
  kms_key_arn = null
  # layers - (optional) is a type of list of string
  layers = []
  # memory_size - (optional) is a type of number
  memory_size = null
  # package_type - (optional) is a type of string
  package_type = null
  # publish - (optional) is a type of bool
  publish = null
  # reserved_concurrent_executions - (optional) is a type of number
  reserved_concurrent_executions = null
  # role - (required) is a type of string
  role = null
  # runtime - (optional) is a type of string
  runtime = null
  # s3_bucket - (optional) is a type of string
  s3_bucket = null
  # s3_key - (optional) is a type of string
  s3_key = null
  # s3_object_version - (optional) is a type of string
  s3_object_version = null
  # source_code_hash - (optional) is a type of string
  source_code_hash = null
  # tags - (optional) is a type of map of string
  tags = {}
  # timeout - (optional) is a type of number
  timeout = null

  dead_letter_config = [{
    target_arn = null
  }]

  environment = [{
    variables = {}
  }]

  file_system_config = [{
    arn              = null
    local_mount_path = null
  }]

  image_config = [{
    command           = []
    entry_point       = []
    working_directory = null
  }]

  timeouts = [{
    create = null
  }]

  tracing_config = [{
    mode = null
  }]

  vpc_config = [{
    security_group_ids = []
    subnet_ids         = []
    vpc_id             = null
  }]
}
```
[top](#index)
### Variables
```hcl
variable "code_signing_config_arn" {
  description = "(optional)"
  type        = string
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

variable "function_name" {
  description = "(required)"
  type        = string
}

variable "handler" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "image_uri" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "kms_key_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "layers" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "memory_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "package_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "publish" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "reserved_concurrent_executions" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "role" {
  description = "(required)"
  type        = string
}

variable "runtime" {
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

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dead_letter_config" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      target_arn = string
    }
  ))
  default = []
}

variable "environment" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      variables = map(string)
    }
  ))
  default = []
}

variable "file_system_config" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      arn              = string
      local_mount_path = string
    }
  ))
  default = []
}

variable "image_config" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      command           = list(string)
      entry_point       = list(string)
      working_directory = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
    }
  ))
  default = []
}

variable "tracing_config" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      mode = string
    }
  ))
  default = []
}

variable "vpc_config" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      security_group_ids = set(string)
      subnet_ids         = set(string)
      vpc_id             = string
    }
  ))
  default = []
}
```
[top](#index)

### Resource
```hcl
resource "aws_lambda_function" "this" {
  code_signing_config_arn        = var.code_signing_config_arn
  description                    = var.description
  filename                       = var.filename
  function_name                  = var.function_name
  handler                        = var.handler
  image_uri                      = var.image_uri
  kms_key_arn                    = var.kms_key_arn
  layers                         = var.layers
  memory_size                    = var.memory_size
  package_type                   = var.package_type
  publish                        = var.publish
  reserved_concurrent_executions = var.reserved_concurrent_executions
  role                           = var.role
  runtime                        = var.runtime
  s3_bucket                      = var.s3_bucket
  s3_key                         = var.s3_key
  s3_object_version              = var.s3_object_version
  source_code_hash               = var.source_code_hash
  tags                           = var.tags
  timeout                        = var.timeout

  dynamic "dead_letter_config" {
    for_each = var.dead_letter_config
    content {
      target_arn = dead_letter_config.value["target_arn"]
    }
  }

  dynamic "environment" {
    for_each = var.environment
    content {
      variables = environment.value["variables"]
    }
  }

  dynamic "file_system_config" {
    for_each = var.file_system_config
    content {
      arn              = file_system_config.value["arn"]
      local_mount_path = file_system_config.value["local_mount_path"]
    }
  }

  dynamic "image_config" {
    for_each = var.image_config
    content {
      command           = image_config.value["command"]
      entry_point       = image_config.value["entry_point"]
      working_directory = image_config.value["working_directory"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
    }
  }

  dynamic "tracing_config" {
    for_each = var.tracing_config
    content {
      mode = tracing_config.value["mode"]
    }
  }

  dynamic "vpc_config" {
    for_each = var.vpc_config
    content {
      security_group_ids = vpc_config.value["security_group_ids"]
      subnet_ids         = vpc_config.value["subnet_ids"]
    }
  }

}
```
[top](#index)
### Outputs
```hcl
output "arn" {
  description = "returns a string"
  value       = aws_lambda_function.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_lambda_function.this.id
}

output "invoke_arn" {
  description = "returns a string"
  value       = aws_lambda_function.this.invoke_arn
}

output "last_modified" {
  description = "returns a string"
  value       = aws_lambda_function.this.last_modified
}

output "qualified_arn" {
  description = "returns a string"
  value       = aws_lambda_function.this.qualified_arn
}

output "signing_job_arn" {
  description = "returns a string"
  value       = aws_lambda_function.this.signing_job_arn
}

output "signing_profile_version_arn" {
  description = "returns a string"
  value       = aws_lambda_function.this.signing_profile_version_arn
}

output "source_code_hash" {
  description = "returns a string"
  value       = aws_lambda_function.this.source_code_hash
}

output "source_code_size" {
  description = "returns a number"
  value       = aws_lambda_function.this.source_code_size
}

output "version" {
  description = "returns a string"
  value       = aws_lambda_function.this.version
}

output "this" {
  value = aws_lambda_function.this
}
```
[top](#index)
