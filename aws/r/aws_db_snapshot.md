# aws_db_snapshot

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
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_db_snapshot" {
  source = "./modules/aws/r/aws_db_snapshot"

  # db_instance_identifier - (required) is a type of string
  db_instance_identifier = null
  # db_snapshot_identifier - (required) is a type of string
  db_snapshot_identifier = null
  # tags - (optional) is a type of map of string
  tags = {}

  timeouts = [{
    read = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "db_instance_identifier" {
  description = "(required)"
  type        = string
}

variable "db_snapshot_identifier" {
  description = "(required)"
  type        = string
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
      read = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_db_snapshot" "this" {
  db_instance_identifier = var.db_instance_identifier
  db_snapshot_identifier = var.db_snapshot_identifier
  tags                   = var.tags

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      read = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "allocated_storage" {
  description = "returns a number"
  value       = aws_db_snapshot.this.allocated_storage
}

output "availability_zone" {
  description = "returns a string"
  value       = aws_db_snapshot.this.availability_zone
}

output "db_snapshot_arn" {
  description = "returns a string"
  value       = aws_db_snapshot.this.db_snapshot_arn
}

output "encrypted" {
  description = "returns a bool"
  value       = aws_db_snapshot.this.encrypted
}

output "engine" {
  description = "returns a string"
  value       = aws_db_snapshot.this.engine
}

output "engine_version" {
  description = "returns a string"
  value       = aws_db_snapshot.this.engine_version
}

output "id" {
  description = "returns a string"
  value       = aws_db_snapshot.this.id
}

output "iops" {
  description = "returns a number"
  value       = aws_db_snapshot.this.iops
}

output "kms_key_id" {
  description = "returns a string"
  value       = aws_db_snapshot.this.kms_key_id
}

output "license_model" {
  description = "returns a string"
  value       = aws_db_snapshot.this.license_model
}

output "option_group_name" {
  description = "returns a string"
  value       = aws_db_snapshot.this.option_group_name
}

output "port" {
  description = "returns a number"
  value       = aws_db_snapshot.this.port
}

output "snapshot_type" {
  description = "returns a string"
  value       = aws_db_snapshot.this.snapshot_type
}

output "source_db_snapshot_identifier" {
  description = "returns a string"
  value       = aws_db_snapshot.this.source_db_snapshot_identifier
}

output "source_region" {
  description = "returns a string"
  value       = aws_db_snapshot.this.source_region
}

output "status" {
  description = "returns a string"
  value       = aws_db_snapshot.this.status
}

output "storage_type" {
  description = "returns a string"
  value       = aws_db_snapshot.this.storage_type
}

output "vpc_id" {
  description = "returns a string"
  value       = aws_db_snapshot.this.vpc_id
}

output "this" {
  value = aws_db_snapshot.this
}
```

[top](#index)