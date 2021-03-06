# aws_ebs_snapshot_ids

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
module "aws_ebs_snapshot_ids" {
  source = "./modules/aws/d/aws_ebs_snapshot_ids"

  # owners - (optional) is a type of list of string
  owners = []
  # restorable_by_user_ids - (optional) is a type of list of string
  restorable_by_user_ids = []

  filter = [{
    name   = null
    values = []
  }]
}
```

[top](#index)

### Variables

```terraform
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
data "aws_ebs_snapshot_ids" "this" {
  # owners - (optional) is a type of list of string
  owners = var.owners
  # restorable_by_user_ids - (optional) is a type of list of string
  restorable_by_user_ids = var.restorable_by_user_ids

  dynamic "filter" {
    for_each = var.filter
    content {
      # name - (required) is a type of string
      name = filter.value["name"]
      # values - (required) is a type of list of string
      values = filter.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.aws_ebs_snapshot_ids.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.aws_ebs_snapshot_ids.this.ids
}

output "this" {
  value = aws_ebs_snapshot_ids.this
}
```

[top](#index)