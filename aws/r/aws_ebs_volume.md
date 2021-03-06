# aws_ebs_volume

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
module "aws_ebs_volume" {
  source = "./modules/aws/r/aws_ebs_volume"

  # availability_zone - (required) is a type of string
  availability_zone = null
  # encrypted - (optional) is a type of bool
  encrypted = null
  # iops - (optional) is a type of number
  iops = null
  # kms_key_id - (optional) is a type of string
  kms_key_id = null
  # multi_attach_enabled - (optional) is a type of bool
  multi_attach_enabled = null
  # outpost_arn - (optional) is a type of string
  outpost_arn = null
  # size - (optional) is a type of number
  size = null
  # snapshot_id - (optional) is a type of string
  snapshot_id = null
  # tags - (optional) is a type of map of string
  tags = {}
  # throughput - (optional) is a type of number
  throughput = null
  # type - (optional) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "availability_zone" {
  description = "(required)"
  type        = string
}

variable "encrypted" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "iops" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "kms_key_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "multi_attach_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "outpost_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "snapshot_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "throughput" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_ebs_volume" "this" {
  # availability_zone - (required) is a type of string
  availability_zone = var.availability_zone
  # encrypted - (optional) is a type of bool
  encrypted = var.encrypted
  # iops - (optional) is a type of number
  iops = var.iops
  # kms_key_id - (optional) is a type of string
  kms_key_id = var.kms_key_id
  # multi_attach_enabled - (optional) is a type of bool
  multi_attach_enabled = var.multi_attach_enabled
  # outpost_arn - (optional) is a type of string
  outpost_arn = var.outpost_arn
  # size - (optional) is a type of number
  size = var.size
  # snapshot_id - (optional) is a type of string
  snapshot_id = var.snapshot_id
  # tags - (optional) is a type of map of string
  tags = var.tags
  # throughput - (optional) is a type of number
  throughput = var.throughput
  # type - (optional) is a type of string
  type = var.type
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_ebs_volume.this.arn
}

output "encrypted" {
  description = "returns a bool"
  value       = aws_ebs_volume.this.encrypted
}

output "id" {
  description = "returns a string"
  value       = aws_ebs_volume.this.id
}

output "iops" {
  description = "returns a number"
  value       = aws_ebs_volume.this.iops
}

output "kms_key_id" {
  description = "returns a string"
  value       = aws_ebs_volume.this.kms_key_id
}

output "size" {
  description = "returns a number"
  value       = aws_ebs_volume.this.size
}

output "snapshot_id" {
  description = "returns a string"
  value       = aws_ebs_volume.this.snapshot_id
}

output "throughput" {
  description = "returns a number"
  value       = aws_ebs_volume.this.throughput
}

output "type" {
  description = "returns a string"
  value       = aws_ebs_volume.this.type
}

output "this" {
  value = aws_ebs_volume.this
}
```

[top](#index)