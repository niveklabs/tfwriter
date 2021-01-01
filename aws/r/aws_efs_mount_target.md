# aws_efs_mount_target
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
module "aws_efs_mount_target" {
  source = "./modules/aws/r/aws_efs_mount_target"

  # file_system_id - (required) is a type of string
  file_system_id = null
  # ip_address - (optional) is a type of string
  ip_address = null
  # security_groups - (optional) is a type of set of string
  security_groups = []
  # subnet_id - (required) is a type of string
  subnet_id = null
}
```
[top](#index)
### Variables
```hcl
variable "file_system_id" {
  description = "(required)"
  type        = string
}

variable "ip_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_groups" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "subnet_id" {
  description = "(required)"
  type        = string
}
```
[top](#index)

### Resource
```hcl
resource "aws_efs_mount_target" "this" {
  file_system_id  = var.file_system_id
  ip_address      = var.ip_address
  security_groups = var.security_groups
  subnet_id       = var.subnet_id
}
```
[top](#index)
### Outputs
```hcl
output "availability_zone_id" {
  description = "returns a string"
  value       = aws_efs_mount_target.this.availability_zone_id
}

output "availability_zone_name" {
  description = "returns a string"
  value       = aws_efs_mount_target.this.availability_zone_name
}

output "dns_name" {
  description = "returns a string"
  value       = aws_efs_mount_target.this.dns_name
}

output "file_system_arn" {
  description = "returns a string"
  value       = aws_efs_mount_target.this.file_system_arn
}

output "id" {
  description = "returns a string"
  value       = aws_efs_mount_target.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = aws_efs_mount_target.this.ip_address
}

output "mount_target_dns_name" {
  description = "returns a string"
  value       = aws_efs_mount_target.this.mount_target_dns_name
}

output "network_interface_id" {
  description = "returns a string"
  value       = aws_efs_mount_target.this.network_interface_id
}

output "owner_id" {
  description = "returns a string"
  value       = aws_efs_mount_target.this.owner_id
}

output "security_groups" {
  description = "returns a set of string"
  value       = aws_efs_mount_target.this.security_groups
}

output "this" {
  value = aws_efs_mount_target.this
}
```
[top](#index)
