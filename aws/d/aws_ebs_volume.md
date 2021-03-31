# aws_ebs_volume

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
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_ebs_volume" {
  source = "./modules/aws/d/aws_ebs_volume"

  # most_recent - (optional) is a type of bool
  most_recent = null
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

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "filter" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
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
data "aws_ebs_volume" "this" {
  most_recent = var.most_recent
  tags        = var.tags

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
  value       = data.aws_ebs_volume.this.arn
}

output "availability_zone" {
  description = "returns a string"
  value       = data.aws_ebs_volume.this.availability_zone
}

output "encrypted" {
  description = "returns a bool"
  value       = data.aws_ebs_volume.this.encrypted
}

output "id" {
  description = "returns a string"
  value       = data.aws_ebs_volume.this.id
}

output "iops" {
  description = "returns a number"
  value       = data.aws_ebs_volume.this.iops
}

output "kms_key_id" {
  description = "returns a string"
  value       = data.aws_ebs_volume.this.kms_key_id
}

output "multi_attach_enabled" {
  description = "returns a bool"
  value       = data.aws_ebs_volume.this.multi_attach_enabled
}

output "outpost_arn" {
  description = "returns a string"
  value       = data.aws_ebs_volume.this.outpost_arn
}

output "size" {
  description = "returns a number"
  value       = data.aws_ebs_volume.this.size
}

output "snapshot_id" {
  description = "returns a string"
  value       = data.aws_ebs_volume.this.snapshot_id
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_ebs_volume.this.tags
}

output "throughput" {
  description = "returns a number"
  value       = data.aws_ebs_volume.this.throughput
}

output "volume_id" {
  description = "returns a string"
  value       = data.aws_ebs_volume.this.volume_id
}

output "volume_type" {
  description = "returns a string"
  value       = data.aws_ebs_volume.this.volume_type
}

output "this" {
  value = aws_ebs_volume.this
}
```

[top](#index)