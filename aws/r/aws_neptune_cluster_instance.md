# aws_neptune_cluster_instance

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
module "aws_neptune_cluster_instance" {
  source = "./modules/aws/r/aws_neptune_cluster_instance"

  # apply_immediately - (optional) is a type of bool
  apply_immediately = null
  # auto_minor_version_upgrade - (optional) is a type of bool
  auto_minor_version_upgrade = null
  # availability_zone - (optional) is a type of string
  availability_zone = null
  # cluster_identifier - (required) is a type of string
  cluster_identifier = null
  # engine - (optional) is a type of string
  engine = null
  # engine_version - (optional) is a type of string
  engine_version = null
  # identifier - (optional) is a type of string
  identifier = null
  # identifier_prefix - (optional) is a type of string
  identifier_prefix = null
  # instance_class - (required) is a type of string
  instance_class = null
  # neptune_parameter_group_name - (optional) is a type of string
  neptune_parameter_group_name = null
  # neptune_subnet_group_name - (optional) is a type of string
  neptune_subnet_group_name = null
  # port - (optional) is a type of number
  port = null
  # preferred_backup_window - (optional) is a type of string
  preferred_backup_window = null
  # preferred_maintenance_window - (optional) is a type of string
  preferred_maintenance_window = null
  # promotion_tier - (optional) is a type of number
  promotion_tier = null
  # publicly_accessible - (optional) is a type of bool
  publicly_accessible = null
  # tags - (optional) is a type of map of string
  tags = {}

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

variable "cluster_identifier" {
  description = "(required)"
  type        = string
}

variable "engine" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "engine_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "identifier" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "identifier_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_class" {
  description = "(required)"
  type        = string
}

variable "neptune_parameter_group_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "neptune_subnet_group_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "preferred_backup_window" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "preferred_maintenance_window" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "promotion_tier" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "publicly_accessible" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
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
resource "aws_neptune_cluster_instance" "this" {
  apply_immediately            = var.apply_immediately
  auto_minor_version_upgrade   = var.auto_minor_version_upgrade
  availability_zone            = var.availability_zone
  cluster_identifier           = var.cluster_identifier
  engine                       = var.engine
  engine_version               = var.engine_version
  identifier                   = var.identifier
  identifier_prefix            = var.identifier_prefix
  instance_class               = var.instance_class
  neptune_parameter_group_name = var.neptune_parameter_group_name
  neptune_subnet_group_name    = var.neptune_subnet_group_name
  port                         = var.port
  preferred_backup_window      = var.preferred_backup_window
  preferred_maintenance_window = var.preferred_maintenance_window
  promotion_tier               = var.promotion_tier
  publicly_accessible          = var.publicly_accessible
  tags                         = var.tags

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
output "address" {
  description = "returns a string"
  value       = aws_neptune_cluster_instance.this.address
}

output "apply_immediately" {
  description = "returns a bool"
  value       = aws_neptune_cluster_instance.this.apply_immediately
}

output "arn" {
  description = "returns a string"
  value       = aws_neptune_cluster_instance.this.arn
}

output "availability_zone" {
  description = "returns a string"
  value       = aws_neptune_cluster_instance.this.availability_zone
}

output "dbi_resource_id" {
  description = "returns a string"
  value       = aws_neptune_cluster_instance.this.dbi_resource_id
}

output "endpoint" {
  description = "returns a string"
  value       = aws_neptune_cluster_instance.this.endpoint
}

output "engine_version" {
  description = "returns a string"
  value       = aws_neptune_cluster_instance.this.engine_version
}

output "id" {
  description = "returns a string"
  value       = aws_neptune_cluster_instance.this.id
}

output "identifier" {
  description = "returns a string"
  value       = aws_neptune_cluster_instance.this.identifier
}

output "identifier_prefix" {
  description = "returns a string"
  value       = aws_neptune_cluster_instance.this.identifier_prefix
}

output "kms_key_arn" {
  description = "returns a string"
  value       = aws_neptune_cluster_instance.this.kms_key_arn
}

output "neptune_subnet_group_name" {
  description = "returns a string"
  value       = aws_neptune_cluster_instance.this.neptune_subnet_group_name
}

output "preferred_backup_window" {
  description = "returns a string"
  value       = aws_neptune_cluster_instance.this.preferred_backup_window
}

output "preferred_maintenance_window" {
  description = "returns a string"
  value       = aws_neptune_cluster_instance.this.preferred_maintenance_window
}

output "storage_encrypted" {
  description = "returns a bool"
  value       = aws_neptune_cluster_instance.this.storage_encrypted
}

output "writer" {
  description = "returns a bool"
  value       = aws_neptune_cluster_instance.this.writer
}

output "this" {
  value = aws_neptune_cluster_instance.this
}
```

[top](#index)