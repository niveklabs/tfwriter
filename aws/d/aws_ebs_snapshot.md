# aws_ebs_snapshot

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_ebs_snapshot" {
  source = "./modules/aws/d/aws_ebs_snapshot"

  # most_recent - (optional) is a type of bool
  most_recent = null
  # owners - (optional) is a type of list of string
  owners = []
  # restorable_by_user_ids - (optional) is a type of list of string
  restorable_by_user_ids = []
  # snapshot_ids - (optional) is a type of list of string
  snapshot_ids = []
  # tags - (optional) is a type of map of string
  tags = {}

  filter = [{
    name   = null
    values = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "most_recent" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "owners" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "restorable_by_user_ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "snapshot_ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "filter" {
  description = "nested mode: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name   = string
      values = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "aws_ebs_snapshot" "this" {
  most_recent            = var.most_recent
  owners                 = var.owners
  restorable_by_user_ids = var.restorable_by_user_ids
  snapshot_ids           = var.snapshot_ids
  tags                   = var.tags

  dynamic "filter" {
    for_each = var.filter
    content {
      name   = filter.value["name"]
      values = filter.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = data.aws_ebs_snapshot.this.arn
}

output "data_encryption_key_id" {
  description = "returns a string"
  value       = data.aws_ebs_snapshot.this.data_encryption_key_id
}

output "description" {
  description = "returns a string"
  value       = data.aws_ebs_snapshot.this.description
}

output "encrypted" {
  description = "returns a bool"
  value       = data.aws_ebs_snapshot.this.encrypted
}

output "id" {
  description = "returns a string"
  value       = data.aws_ebs_snapshot.this.id
}

output "kms_key_id" {
  description = "returns a string"
  value       = data.aws_ebs_snapshot.this.kms_key_id
}

output "owner_alias" {
  description = "returns a string"
  value       = data.aws_ebs_snapshot.this.owner_alias
}

output "owner_id" {
  description = "returns a string"
  value       = data.aws_ebs_snapshot.this.owner_id
}

output "snapshot_id" {
  description = "returns a string"
  value       = data.aws_ebs_snapshot.this.snapshot_id
}

output "state" {
  description = "returns a string"
  value       = data.aws_ebs_snapshot.this.state
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_ebs_snapshot.this.tags
}

output "volume_id" {
  description = "returns a string"
  value       = data.aws_ebs_snapshot.this.volume_id
}

output "volume_size" {
  description = "returns a number"
  value       = data.aws_ebs_snapshot.this.volume_size
}

output "this" {
  value = aws_ebs_snapshot.this
}
```

[top](#index)