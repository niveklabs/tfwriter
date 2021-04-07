# aws_resourcegroups_group

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
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
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

```terraform
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
  description = "nested block: NestingList, min items: 1, max items: 1"
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

```terraform
resource "aws_resourcegroups_group" "this" {
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "resource_query" {
    for_each = var.resource_query
    content {
      # query - (required) is a type of string
      query = resource_query.value["query"]
      # type - (optional) is a type of string
      type = resource_query.value["type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
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