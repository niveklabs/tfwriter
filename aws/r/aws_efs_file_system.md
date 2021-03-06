# aws_efs_file_system

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
module "aws_efs_file_system" {
  source = "./modules/aws/r/aws_efs_file_system"

  # availability_zone_name - (optional) is a type of string
  availability_zone_name = null
  # creation_token - (optional) is a type of string
  creation_token = null
  # encrypted - (optional) is a type of bool
  encrypted = null
  # kms_key_id - (optional) is a type of string
  kms_key_id = null
  # performance_mode - (optional) is a type of string
  performance_mode = null
  # provisioned_throughput_in_mibps - (optional) is a type of number
  provisioned_throughput_in_mibps = null
  # tags - (optional) is a type of map of string
  tags = {}
  # throughput_mode - (optional) is a type of string
  throughput_mode = null

  lifecycle_policy = [{
    transition_to_ia = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "availability_zone_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "creation_token" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "encrypted" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "kms_key_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "performance_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "provisioned_throughput_in_mibps" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "throughput_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "lifecycle_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      transition_to_ia = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_efs_file_system" "this" {
  # availability_zone_name - (optional) is a type of string
  availability_zone_name = var.availability_zone_name
  # creation_token - (optional) is a type of string
  creation_token = var.creation_token
  # encrypted - (optional) is a type of bool
  encrypted = var.encrypted
  # kms_key_id - (optional) is a type of string
  kms_key_id = var.kms_key_id
  # performance_mode - (optional) is a type of string
  performance_mode = var.performance_mode
  # provisioned_throughput_in_mibps - (optional) is a type of number
  provisioned_throughput_in_mibps = var.provisioned_throughput_in_mibps
  # tags - (optional) is a type of map of string
  tags = var.tags
  # throughput_mode - (optional) is a type of string
  throughput_mode = var.throughput_mode

  dynamic "lifecycle_policy" {
    for_each = var.lifecycle_policy
    content {
      # transition_to_ia - (required) is a type of string
      transition_to_ia = lifecycle_policy.value["transition_to_ia"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_efs_file_system.this.arn
}

output "availability_zone_id" {
  description = "returns a string"
  value       = aws_efs_file_system.this.availability_zone_id
}

output "availability_zone_name" {
  description = "returns a string"
  value       = aws_efs_file_system.this.availability_zone_name
}

output "creation_token" {
  description = "returns a string"
  value       = aws_efs_file_system.this.creation_token
}

output "dns_name" {
  description = "returns a string"
  value       = aws_efs_file_system.this.dns_name
}

output "encrypted" {
  description = "returns a bool"
  value       = aws_efs_file_system.this.encrypted
}

output "id" {
  description = "returns a string"
  value       = aws_efs_file_system.this.id
}

output "kms_key_id" {
  description = "returns a string"
  value       = aws_efs_file_system.this.kms_key_id
}

output "number_of_mount_targets" {
  description = "returns a number"
  value       = aws_efs_file_system.this.number_of_mount_targets
}

output "owner_id" {
  description = "returns a string"
  value       = aws_efs_file_system.this.owner_id
}

output "performance_mode" {
  description = "returns a string"
  value       = aws_efs_file_system.this.performance_mode
}

output "size_in_bytes" {
  description = "returns a list of object"
  value       = aws_efs_file_system.this.size_in_bytes
}

output "this" {
  value = aws_efs_file_system.this
}
```

[top](#index)