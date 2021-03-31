# aws_efs_file_system

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
module "aws_efs_file_system" {
  source = "./modules/aws/d/aws_efs_file_system"

  # creation_token - (optional) is a type of string
  creation_token = null
  # file_system_id - (optional) is a type of string
  file_system_id = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "creation_token" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "file_system_id" {
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
data "aws_efs_file_system" "this" {
  creation_token = var.creation_token
  file_system_id = var.file_system_id
  tags           = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = data.aws_efs_file_system.this.arn
}

output "creation_token" {
  description = "returns a string"
  value       = data.aws_efs_file_system.this.creation_token
}

output "dns_name" {
  description = "returns a string"
  value       = data.aws_efs_file_system.this.dns_name
}

output "encrypted" {
  description = "returns a bool"
  value       = data.aws_efs_file_system.this.encrypted
}

output "file_system_id" {
  description = "returns a string"
  value       = data.aws_efs_file_system.this.file_system_id
}

output "id" {
  description = "returns a string"
  value       = data.aws_efs_file_system.this.id
}

output "kms_key_id" {
  description = "returns a string"
  value       = data.aws_efs_file_system.this.kms_key_id
}

output "lifecycle_policy" {
  description = "returns a list of object"
  value       = data.aws_efs_file_system.this.lifecycle_policy
}

output "performance_mode" {
  description = "returns a string"
  value       = data.aws_efs_file_system.this.performance_mode
}

output "provisioned_throughput_in_mibps" {
  description = "returns a number"
  value       = data.aws_efs_file_system.this.provisioned_throughput_in_mibps
}

output "size_in_bytes" {
  description = "returns a number"
  value       = data.aws_efs_file_system.this.size_in_bytes
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_efs_file_system.this.tags
}

output "throughput_mode" {
  description = "returns a string"
  value       = data.aws_efs_file_system.this.throughput_mode
}

output "this" {
  value = aws_efs_file_system.this
}
```

[top](#index)