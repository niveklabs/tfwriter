# aws_dms_replication_subnet_group

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
module "aws_dms_replication_subnet_group" {
  source = "./modules/aws/r/aws_dms_replication_subnet_group"

  # replication_subnet_group_description - (required) is a type of string
  replication_subnet_group_description = null
  # replication_subnet_group_id - (required) is a type of string
  replication_subnet_group_id = null
  # subnet_ids - (required) is a type of set of string
  subnet_ids = []
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "replication_subnet_group_description" {
  description = "(required)"
  type        = string
}

variable "replication_subnet_group_id" {
  description = "(required)"
  type        = string
}

variable "subnet_ids" {
  description = "(required)"
  type        = set(string)
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_dms_replication_subnet_group" "this" {
  replication_subnet_group_description = var.replication_subnet_group_description
  replication_subnet_group_id          = var.replication_subnet_group_id
  subnet_ids                           = var.subnet_ids
  tags                                 = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_dms_replication_subnet_group.this.id
}

output "replication_subnet_group_arn" {
  description = "returns a string"
  value       = aws_dms_replication_subnet_group.this.replication_subnet_group_arn
}

output "vpc_id" {
  description = "returns a string"
  value       = aws_dms_replication_subnet_group.this.vpc_id
}

output "this" {
  value = aws_dms_replication_subnet_group.this
}
```

[top](#index)