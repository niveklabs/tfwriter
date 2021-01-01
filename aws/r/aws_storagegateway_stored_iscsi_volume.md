# aws_storagegateway_stored_iscsi_volume
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
module "aws_storagegateway_stored_iscsi_volume" {
  source = "./modules/aws/r/aws_storagegateway_stored_iscsi_volume"

  # disk_id - (required) is a type of string
  disk_id = null
  # gateway_arn - (required) is a type of string
  gateway_arn = null
  # kms_encrypted - (optional) is a type of bool
  kms_encrypted = null
  # kms_key - (optional) is a type of string
  kms_key = null
  # network_interface_id - (required) is a type of string
  network_interface_id = null
  # preserve_existing_data - (required) is a type of bool
  preserve_existing_data = null
  # snapshot_id - (optional) is a type of string
  snapshot_id = null
  # tags - (optional) is a type of map of string
  tags = {}
  # target_name - (required) is a type of string
  target_name = null
}
```
[top](#index)
### Variables
```hcl
variable "disk_id" {
  description = "(required)"
  type        = string
}

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

variable "preserve_existing_data" {
  description = "(required)"
  type        = bool
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

variable "target_name" {
  description = "(required)"
  type        = string
}
```
[top](#index)

### Resource
```hcl
resource "aws_storagegateway_stored_iscsi_volume" "this" {
  disk_id                = var.disk_id
  gateway_arn            = var.gateway_arn
  kms_encrypted          = var.kms_encrypted
  kms_key                = var.kms_key
  network_interface_id   = var.network_interface_id
  preserve_existing_data = var.preserve_existing_data
  snapshot_id            = var.snapshot_id
  tags                   = var.tags
  target_name            = var.target_name
}
```
[top](#index)
### Outputs
```hcl
output "arn" {
  description = "returns a string"
  value       = aws_storagegateway_stored_iscsi_volume.this.arn
}

output "chap_enabled" {
  description = "returns a bool"
  value       = aws_storagegateway_stored_iscsi_volume.this.chap_enabled
}

output "id" {
  description = "returns a string"
  value       = aws_storagegateway_stored_iscsi_volume.this.id
}

output "lun_number" {
  description = "returns a number"
  value       = aws_storagegateway_stored_iscsi_volume.this.lun_number
}

output "network_interface_port" {
  description = "returns a number"
  value       = aws_storagegateway_stored_iscsi_volume.this.network_interface_port
}

output "target_arn" {
  description = "returns a string"
  value       = aws_storagegateway_stored_iscsi_volume.this.target_arn
}

output "volume_attachment_status" {
  description = "returns a string"
  value       = aws_storagegateway_stored_iscsi_volume.this.volume_attachment_status
}

output "volume_id" {
  description = "returns a string"
  value       = aws_storagegateway_stored_iscsi_volume.this.volume_id
}

output "volume_size_in_bytes" {
  description = "returns a number"
  value       = aws_storagegateway_stored_iscsi_volume.this.volume_size_in_bytes
}

output "volume_status" {
  description = "returns a string"
  value       = aws_storagegateway_stored_iscsi_volume.this.volume_status
}

output "volume_type" {
  description = "returns a string"
  value       = aws_storagegateway_stored_iscsi_volume.this.volume_type
}

output "this" {
  value = aws_storagegateway_stored_iscsi_volume.this
}
```
[top](#index)
