# aws_efs_mount_target

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
module "aws_efs_mount_target" {
  source = "./modules/aws/d/aws_efs_mount_target"

  # mount_target_id - (required) is a type of string
  mount_target_id = null
}
```

[top](#index)

### Variables

```terraform
variable "mount_target_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "aws_efs_mount_target" "this" {
  mount_target_id = var.mount_target_id
}
```

[top](#index)

### Outputs

```terraform
output "availability_zone_id" {
  description = "returns a string"
  value       = data.aws_efs_mount_target.this.availability_zone_id
}

output "availability_zone_name" {
  description = "returns a string"
  value       = data.aws_efs_mount_target.this.availability_zone_name
}

output "dns_name" {
  description = "returns a string"
  value       = data.aws_efs_mount_target.this.dns_name
}

output "file_system_arn" {
  description = "returns a string"
  value       = data.aws_efs_mount_target.this.file_system_arn
}

output "file_system_id" {
  description = "returns a string"
  value       = data.aws_efs_mount_target.this.file_system_id
}

output "id" {
  description = "returns a string"
  value       = data.aws_efs_mount_target.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = data.aws_efs_mount_target.this.ip_address
}

output "mount_target_dns_name" {
  description = "returns a string"
  value       = data.aws_efs_mount_target.this.mount_target_dns_name
}

output "network_interface_id" {
  description = "returns a string"
  value       = data.aws_efs_mount_target.this.network_interface_id
}

output "owner_id" {
  description = "returns a string"
  value       = data.aws_efs_mount_target.this.owner_id
}

output "security_groups" {
  description = "returns a set of string"
  value       = data.aws_efs_mount_target.this.security_groups
}

output "subnet_id" {
  description = "returns a string"
  value       = data.aws_efs_mount_target.this.subnet_id
}

output "this" {
  value = aws_efs_mount_target.this
}
```

[top](#index)