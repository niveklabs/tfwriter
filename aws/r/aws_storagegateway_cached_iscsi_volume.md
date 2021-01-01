# aws_storagegateway_cached_iscsi_volume

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "aws_storagegateway_cached_iscsi_volume" {
  source = "./modules/aws/r/aws_storagegateway_cached_iscsi_volume"

  # gateway_arn - (required) is a type of string
  gateway_arn = null
  # kms_encrypted - (optional) is a type of bool
  kms_encrypted = null
  # kms_key - (optional) is a type of string
  kms_key = null
  # network_interface_id - (required) is a type of string
  network_interface_id = null
  # snapshot_id - (optional) is a type of string
  snapshot_id = null
  # source_volume_arn - (optional) is a type of string
  source_volume_arn = null
  # tags - (optional) is a type of map of string
  tags = {}
  # target_name - (required) is a type of string
  target_name = null
  # volume_size_in_bytes - (required) is a type of number
  volume_size_in_bytes = null
}
```

[top](#index)

### Variables

```hcl
variable "gateway_arn" {
  description = "(required)"
  type        = string
}

variable "kms_encrypted" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "kms_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "network_interface_id" {
  description = "(required)"
  type        = string
}

variable "snapshot_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_volume_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "target_name" {
  description = "(required)"
  type        = string
}

variable "volume_size_in_bytes" {
  description = "(required)"
  type        = number
}
```

[top](#index)

### Resource

```hcl
resource "aws_storagegateway_cached_iscsi_volume" "this" {
  gateway_arn          = var.gateway_arn
  kms_encrypted        = var.kms_encrypted
  kms_key              = var.kms_key
  network_interface_id = var.network_interface_id
  snapshot_id          = var.snapshot_id
  source_volume_arn    = var.source_volume_arn
  tags                 = var.tags
  target_name          = var.target_name
  volume_size_in_bytes = var.volume_size_in_bytes
}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = aws_storagegateway_cached_iscsi_volume.this.arn
}

output "chap_enabled" {
  description = "returns a bool"
  value       = aws_storagegateway_cached_iscsi_volume.this.chap_enabled
}

output "id" {
  description = "returns a string"
  value       = aws_storagegateway_cached_iscsi_volume.this.id
}

output "lun_number" {
  description = "returns a number"
  value       = aws_storagegateway_cached_iscsi_volume.this.lun_number
}

output "network_interface_port" {
  description = "returns a number"
  value       = aws_storagegateway_cached_iscsi_volume.this.network_interface_port
}

output "target_arn" {
  description = "returns a string"
  value       = aws_storagegateway_cached_iscsi_volume.this.target_arn
}

output "volume_arn" {
  description = "returns a string"
  value       = aws_storagegateway_cached_iscsi_volume.this.volume_arn
}

output "volume_id" {
  description = "returns a string"
  value       = aws_storagegateway_cached_iscsi_volume.this.volume_id
}

output "this" {
  value = aws_storagegateway_cached_iscsi_volume.this
}
```

[top](#index)