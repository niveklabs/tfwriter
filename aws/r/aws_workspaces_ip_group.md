# aws_workspaces_ip_group

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
module "aws_workspaces_ip_group" {
  source = "./modules/aws/r/aws_workspaces_ip_group"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}

  rules = [{
    description = null
    source      = null
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

variable "rules" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      description = string
      source      = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_workspaces_ip_group" "this" {
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "rules" {
    for_each = var.rules
    content {
      # description - (optional) is a type of string
      description = rules.value["description"]
      # source - (required) is a type of string
      source = rules.value["source"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_workspaces_ip_group.this.id
}

output "this" {
  value = aws_workspaces_ip_group.this
}
```

[top](#index)