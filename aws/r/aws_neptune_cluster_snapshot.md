# aws_neptune_cluster_snapshot

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
module "aws_neptune_cluster_snapshot" {
  source = "./modules/aws/r/aws_neptune_cluster_snapshot"

  # db_cluster_identifier - (required) is a type of string
  db_cluster_identifier = null
  # db_cluster_snapshot_identifier - (required) is a type of string
  db_cluster_snapshot_identifier = null

  timeouts = [{
    create = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "db_cluster_identifier" {
  description = "(required)"
  type        = string
}

variable "db_cluster_snapshot_identifier" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```hcl
resource "aws_neptune_cluster_snapshot" "this" {
  db_cluster_identifier          = var.db_cluster_identifier
  db_cluster_snapshot_identifier = var.db_cluster_snapshot_identifier

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "allocated_storage" {
  description = "returns a number"
  value       = aws_neptune_cluster_snapshot.this.allocated_storage
}

output "availability_zones" {
  description = "returns a list of string"
  value       = aws_neptune_cluster_snapshot.this.availability_zones
}

output "db_cluster_snapshot_arn" {
  description = "returns a string"
  value       = aws_neptune_cluster_snapshot.this.db_cluster_snapshot_arn
}

output "engine" {
  description = "returns a string"
  value       = aws_neptune_cluster_snapshot.this.engine
}

output "engine_version" {
  description = "returns a string"
  value       = aws_neptune_cluster_snapshot.this.engine_version
}

output "id" {
  description = "returns a string"
  value       = aws_neptune_cluster_snapshot.this.id
}

output "kms_key_id" {
  description = "returns a string"
  value       = aws_neptune_cluster_snapshot.this.kms_key_id
}

output "license_model" {
  description = "returns a string"
  value       = aws_neptune_cluster_snapshot.this.license_model
}

output "port" {
  description = "returns a number"
  value       = aws_neptune_cluster_snapshot.this.port
}

output "snapshot_type" {
  description = "returns a string"
  value       = aws_neptune_cluster_snapshot.this.snapshot_type
}

output "source_db_cluster_snapshot_arn" {
  description = "returns a string"
  value       = aws_neptune_cluster_snapshot.this.source_db_cluster_snapshot_arn
}

output "status" {
  description = "returns a string"
  value       = aws_neptune_cluster_snapshot.this.status
}

output "storage_encrypted" {
  description = "returns a bool"
  value       = aws_neptune_cluster_snapshot.this.storage_encrypted
}

output "vpc_id" {
  description = "returns a string"
  value       = aws_neptune_cluster_snapshot.this.vpc_id
}

output "this" {
  value = aws_neptune_cluster_snapshot.this
}
```

[top](#index)