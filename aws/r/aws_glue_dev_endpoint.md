# aws_glue_dev_endpoint

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
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_glue_dev_endpoint" {
  source = "./modules/aws/r/aws_glue_dev_endpoint"

  # arguments - (optional) is a type of map of string
  arguments = {}
  # extra_jars_s3_path - (optional) is a type of string
  extra_jars_s3_path = null
  # extra_python_libs_s3_path - (optional) is a type of string
  extra_python_libs_s3_path = null
  # glue_version - (optional) is a type of string
  glue_version = null
  # name - (required) is a type of string
  name = null
  # number_of_nodes - (optional) is a type of number
  number_of_nodes = null
  # number_of_workers - (optional) is a type of number
  number_of_workers = null
  # public_key - (optional) is a type of string
  public_key = null
  # public_keys - (optional) is a type of set of string
  public_keys = []
  # role_arn - (required) is a type of string
  role_arn = null
  # security_configuration - (optional) is a type of string
  security_configuration = null
  # security_group_ids - (optional) is a type of set of string
  security_group_ids = []
  # subnet_id - (optional) is a type of string
  subnet_id = null
  # tags - (optional) is a type of map of string
  tags = {}
  # worker_type - (optional) is a type of string
  worker_type = null
}
```

[top](#index)

### Variables

```terraform
variable "arguments" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "extra_jars_s3_path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "extra_python_libs_s3_path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "glue_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "number_of_nodes" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "number_of_workers" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "public_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "public_keys" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "role_arn" {
  description = "(required)"
  type        = string
}

variable "security_configuration" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_group_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "subnet_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "worker_type" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_glue_dev_endpoint" "this" {
  arguments                 = var.arguments
  extra_jars_s3_path        = var.extra_jars_s3_path
  extra_python_libs_s3_path = var.extra_python_libs_s3_path
  glue_version              = var.glue_version
  name                      = var.name
  number_of_nodes           = var.number_of_nodes
  number_of_workers         = var.number_of_workers
  public_key                = var.public_key
  public_keys               = var.public_keys
  role_arn                  = var.role_arn
  security_configuration    = var.security_configuration
  security_group_ids        = var.security_group_ids
  subnet_id                 = var.subnet_id
  tags                      = var.tags
  worker_type               = var.worker_type
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_glue_dev_endpoint.this.arn
}

output "availability_zone" {
  description = "returns a string"
  value       = aws_glue_dev_endpoint.this.availability_zone
}

output "failure_reason" {
  description = "returns a string"
  value       = aws_glue_dev_endpoint.this.failure_reason
}

output "id" {
  description = "returns a string"
  value       = aws_glue_dev_endpoint.this.id
}

output "private_address" {
  description = "returns a string"
  value       = aws_glue_dev_endpoint.this.private_address
}

output "public_address" {
  description = "returns a string"
  value       = aws_glue_dev_endpoint.this.public_address
}

output "status" {
  description = "returns a string"
  value       = aws_glue_dev_endpoint.this.status
}

output "vpc_id" {
  description = "returns a string"
  value       = aws_glue_dev_endpoint.this.vpc_id
}

output "yarn_endpoint_address" {
  description = "returns a string"
  value       = aws_glue_dev_endpoint.this.yarn_endpoint_address
}

output "zeppelin_remote_spark_interpreter_port" {
  description = "returns a number"
  value       = aws_glue_dev_endpoint.this.zeppelin_remote_spark_interpreter_port
}

output "this" {
  value = aws_glue_dev_endpoint.this
}
```

[top](#index)