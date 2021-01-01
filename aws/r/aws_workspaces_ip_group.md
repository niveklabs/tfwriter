# aws_workspaces_ip_group

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

variable "rules" {
  description = "nested mode: NestingSet, min items: 0, max items: 0"
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

```hcl
resource "aws_workspaces_ip_group" "this" {
  description = var.description
  name        = var.name
  tags        = var.tags

  dynamic "rules" {
    for_each = var.rules
    content {
      description = rules.value["description"]
      source      = rules.value["source"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_workspaces_ip_group.this.id
}

output "this" {
  value = aws_workspaces_ip_group.this
}
```

[top](#index)