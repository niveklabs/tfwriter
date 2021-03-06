# aws_datasync_location_fsx_windows_file_system

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
module "aws_datasync_location_fsx_windows_file_system" {
  source = "./modules/aws/r/aws_datasync_location_fsx_windows_file_system"

  # domain - (optional) is a type of string
  domain = null
  # fsx_filesystem_arn - (required) is a type of string
  fsx_filesystem_arn = null
  # password - (required) is a type of string
  password = null
  # security_group_arns - (required) is a type of set of string
  security_group_arns = []
  # subdirectory - (optional) is a type of string
  subdirectory = null
  # tags - (optional) is a type of map of string
  tags = {}
  # user - (required) is a type of string
  user = null
}
```

[top](#index)

### Variables

```terraform
variable "domain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fsx_filesystem_arn" {
  description = "(required)"
  type        = string
}

variable "password" {
  description = "(required)"
  type        = string
}

variable "security_group_arns" {
  description = "(required)"
  type        = set(string)
}

variable "subdirectory" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "user" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_datasync_location_fsx_windows_file_system" "this" {
  # domain - (optional) is a type of string
  domain = var.domain
  # fsx_filesystem_arn - (required) is a type of string
  fsx_filesystem_arn = var.fsx_filesystem_arn
  # password - (required) is a type of string
  password = var.password
  # security_group_arns - (required) is a type of set of string
  security_group_arns = var.security_group_arns
  # subdirectory - (optional) is a type of string
  subdirectory = var.subdirectory
  # tags - (optional) is a type of map of string
  tags = var.tags
  # user - (required) is a type of string
  user = var.user
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_datasync_location_fsx_windows_file_system.this.arn
}

output "creation_time" {
  description = "returns a string"
  value       = aws_datasync_location_fsx_windows_file_system.this.creation_time
}

output "id" {
  description = "returns a string"
  value       = aws_datasync_location_fsx_windows_file_system.this.id
}

output "subdirectory" {
  description = "returns a string"
  value       = aws_datasync_location_fsx_windows_file_system.this.subdirectory
}

output "uri" {
  description = "returns a string"
  value       = aws_datasync_location_fsx_windows_file_system.this.uri
}

output "this" {
  value = aws_datasync_location_fsx_windows_file_system.this
}
```

[top](#index)