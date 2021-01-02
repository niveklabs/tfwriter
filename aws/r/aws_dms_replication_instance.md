# aws_dms_replication_instance

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_dms_replication_instance" {
  source = "./modules/aws/r/aws_dms_replication_instance"

  # allocated_storage - (optional) is a type of number
  allocated_storage = null
  # allow_major_version_upgrade - (optional) is a type of bool
  allow_major_version_upgrade = null
  # apply_immediately - (optional) is a type of bool
  apply_immediately = null
  # auto_minor_version_upgrade - (optional) is a type of bool
  auto_minor_version_upgrade = null
  # availability_zone - (optional) is a type of string
  availability_zone = null
  # engine_version - (optional) is a type of string
  engine_version = null
  # kms_key_arn - (optional) is a type of string
  kms_key_arn = null
  # multi_az - (optional) is a type of bool
  multi_az = null
  # preferred_maintenance_window - (optional) is a type of string
  preferred_maintenance_window = null
  # publicly_accessible - (optional) is a type of bool
  publicly_accessible = null
  # replication_instance_class - (required) is a type of string
  replication_instance_class = null
  # replication_instance_id - (required) is a type of string
  replication_instance_id = null
  # replication_subnet_group_id - (optional) is a type of string
  replication_subnet_group_id = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vpc_security_group_ids - (optional) is a type of set of string
  vpc_security_group_ids = []

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "allocated_storage" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "allow_major_version_upgrade" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "apply_immediately" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "auto_minor_version_upgrade" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "availability_zone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "engine_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "kms_key_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "multi_az" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "preferred_maintenance_window" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "publicly_accessible" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "replication_instance_class" {
  description = "(required)"
  type        = string
}

variable "replication_instance_id" {
  description = "(required)"
  type        = string
}

variable "replication_subnet_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "vpc_security_group_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_dms_replication_instance" "this" {
  allocated_storage            = var.allocated_storage
  allow_major_version_upgrade  = var.allow_major_version_upgrade
  apply_immediately            = var.apply_immediately
  auto_minor_version_upgrade   = var.auto_minor_version_upgrade
  availability_zone            = var.availability_zone
  engine_version               = var.engine_version
  kms_key_arn                  = var.kms_key_arn
  multi_az                     = var.multi_az
  preferred_maintenance_window = var.preferred_maintenance_window
  publicly_accessible          = var.publicly_accessible
  replication_instance_class   = var.replication_instance_class
  replication_instance_id      = var.replication_instance_id
  replication_subnet_group_id  = var.replication_subnet_group_id
  tags                         = var.tags
  vpc_security_group_ids       = var.vpc_security_group_ids

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "allocated_storage" {
  description = "returns a number"
  value       = aws_dms_replication_instance.this.allocated_storage
}

output "auto_minor_version_upgrade" {
  description = "returns a bool"
  value       = aws_dms_replication_instance.this.auto_minor_version_upgrade
}

output "availability_zone" {
  description = "returns a string"
  value       = aws_dms_replication_instance.this.availability_zone
}

output "engine_version" {
  description = "returns a string"
  value       = aws_dms_replication_instance.this.engine_version
}

output "id" {
  description = "returns a string"
  value       = aws_dms_replication_instance.this.id
}

output "kms_key_arn" {
  description = "returns a string"
  value       = aws_dms_replication_instance.this.kms_key_arn
}

output "multi_az" {
  description = "returns a bool"
  value       = aws_dms_replication_instance.this.multi_az
}

output "preferred_maintenance_window" {
  description = "returns a string"
  value       = aws_dms_replication_instance.this.preferred_maintenance_window
}

output "publicly_accessible" {
  description = "returns a bool"
  value       = aws_dms_replication_instance.this.publicly_accessible
}

output "replication_instance_arn" {
  description = "returns a string"
  value       = aws_dms_replication_instance.this.replication_instance_arn
}

output "replication_instance_private_ips" {
  description = "returns a list of string"
  value       = aws_dms_replication_instance.this.replication_instance_private_ips
}

output "replication_instance_public_ips" {
  description = "returns a list of string"
  value       = aws_dms_replication_instance.this.replication_instance_public_ips
}

output "replication_subnet_group_id" {
  description = "returns a string"
  value       = aws_dms_replication_instance.this.replication_subnet_group_id
}

output "vpc_security_group_ids" {
  description = "returns a set of string"
  value       = aws_dms_replication_instance.this.vpc_security_group_ids
}

output "this" {
  value = aws_dms_replication_instance.this
}
```

[top](#index)