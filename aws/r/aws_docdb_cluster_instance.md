# aws_docdb_cluster_instance

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
module "aws_docdb_cluster_instance" {
  source = "./modules/aws/r/aws_docdb_cluster_instance"

  # apply_immediately - (optional) is a type of bool
  apply_immediately = null
  # auto_minor_version_upgrade - (optional) is a type of bool
  auto_minor_version_upgrade = null
  # availability_zone - (optional) is a type of string
  availability_zone = null
  # ca_cert_identifier - (optional) is a type of string
  ca_cert_identifier = null
  # cluster_identifier - (required) is a type of string
  cluster_identifier = null
  # engine - (optional) is a type of string
  engine = null
  # identifier - (optional) is a type of string
  identifier = null
  # identifier_prefix - (optional) is a type of string
  identifier_prefix = null
  # instance_class - (required) is a type of string
  instance_class = null
  # preferred_maintenance_window - (optional) is a type of string
  preferred_maintenance_window = null
  # promotion_tier - (optional) is a type of number
  promotion_tier = null
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

variable "ca_cert_identifier" {
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

variable "tags" {
  description = "(optional)"
  type        = map(string)
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
resource "aws_docdb_cluster_instance" "this" {
  apply_immediately            = var.apply_immediately
  auto_minor_version_upgrade   = var.auto_minor_version_upgrade
  availability_zone            = var.availability_zone
  ca_cert_identifier           = var.ca_cert_identifier
  cluster_identifier           = var.cluster_identifier
  engine                       = var.engine
  identifier                   = var.identifier
  identifier_prefix            = var.identifier_prefix
  instance_class               = var.instance_class
  preferred_maintenance_window = var.preferred_maintenance_window
  promotion_tier               = var.promotion_tier
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
output "apply_immediately" {
  description = "returns a bool"
  value       = aws_docdb_cluster_instance.this.apply_immediately
}

output "arn" {
  description = "returns a string"
  value       = aws_docdb_cluster_instance.this.arn
}

output "availability_zone" {
  description = "returns a string"
  value       = aws_docdb_cluster_instance.this.availability_zone
}

output "ca_cert_identifier" {
  description = "returns a string"
  value       = aws_docdb_cluster_instance.this.ca_cert_identifier
}

output "db_subnet_group_name" {
  description = "returns a string"
  value       = aws_docdb_cluster_instance.this.db_subnet_group_name
}

output "dbi_resource_id" {
  description = "returns a string"
  value       = aws_docdb_cluster_instance.this.dbi_resource_id
}

output "endpoint" {
  description = "returns a string"
  value       = aws_docdb_cluster_instance.this.endpoint
}

output "engine_version" {
  description = "returns a string"
  value       = aws_docdb_cluster_instance.this.engine_version
}

output "id" {
  description = "returns a string"
  value       = aws_docdb_cluster_instance.this.id
}

output "identifier" {
  description = "returns a string"
  value       = aws_docdb_cluster_instance.this.identifier
}

output "identifier_prefix" {
  description = "returns a string"
  value       = aws_docdb_cluster_instance.this.identifier_prefix
}

output "kms_key_id" {
  description = "returns a string"
  value       = aws_docdb_cluster_instance.this.kms_key_id
}

output "port" {
  description = "returns a number"
  value       = aws_docdb_cluster_instance.this.port
}

output "preferred_backup_window" {
  description = "returns a string"
  value       = aws_docdb_cluster_instance.this.preferred_backup_window
}

output "preferred_maintenance_window" {
  description = "returns a string"
  value       = aws_docdb_cluster_instance.this.preferred_maintenance_window
}

output "publicly_accessible" {
  description = "returns a bool"
  value       = aws_docdb_cluster_instance.this.publicly_accessible
}

output "storage_encrypted" {
  description = "returns a bool"
  value       = aws_docdb_cluster_instance.this.storage_encrypted
}

output "writer" {
  description = "returns a bool"
  value       = aws_docdb_cluster_instance.this.writer
}

output "this" {
  value = aws_docdb_cluster_instance.this
}
```

[top](#index)