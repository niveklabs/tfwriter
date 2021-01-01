# aws_ram_resource_share

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "aws_ram_resource_share" {
  source = "./modules/aws/d/aws_ram_resource_share"

  # name - (required) is a type of string
  name = null
  # resource_owner - (required) is a type of string
  resource_owner = null
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

```hcl
variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_owner" {
  description = "(required)"
  type        = string
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

```hcl
data "aws_ram_resource_share" "this" {
  name           = var.name
  resource_owner = var.resource_owner
  tags           = var.tags

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

```hcl
output "arn" {
  description = "returns a string"
  value       = data.aws_ram_resource_share.this.arn
}

output "id" {
  description = "returns a string"
  value       = data.aws_ram_resource_share.this.id
}

output "owning_account_id" {
  description = "returns a string"
  value       = data.aws_ram_resource_share.this.owning_account_id
}

output "status" {
  description = "returns a string"
  value       = data.aws_ram_resource_share.this.status
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_ram_resource_share.this.tags
}

output "this" {
  value = aws_ram_resource_share.this
}
```

[top](#index)