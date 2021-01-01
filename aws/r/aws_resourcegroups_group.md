# aws_resourcegroups_group

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
module "aws_resourcegroups_group" {
  source = "./modules/aws/r/aws_resourcegroups_group"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}

  resource_query = [{
    query = null
    type  = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "resource_query" {
  description = "nested mode: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      query = string
      type  = string
    }
  ))
}
```

[top](#index)

### Resource

```hcl
resource "aws_resourcegroups_group" "this" {
  description = var.description
  name        = var.name
  tags        = var.tags

  dynamic "resource_query" {
    for_each = var.resource_query
    content {
      query = resource_query.value["query"]
      type  = resource_query.value["type"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = aws_resourcegroups_group.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_resourcegroups_group.this.id
}

output "this" {
  value = aws_resourcegroups_group.this
}
```

[top](#index)