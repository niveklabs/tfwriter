# aws_route53_resolver_rule_association

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
module "aws_route53_resolver_rule_association" {
  source = "./modules/aws/r/aws_route53_resolver_rule_association"

  # name - (optional) is a type of string
  name = null
  # resolver_rule_id - (required) is a type of string
  resolver_rule_id = null
  # vpc_id - (required) is a type of string
  vpc_id = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resolver_rule_id" {
  description = "(required)"
  type        = string
}

variable "vpc_id" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```hcl
resource "aws_route53_resolver_rule_association" "this" {
  name             = var.name
  resolver_rule_id = var.resolver_rule_id
  vpc_id           = var.vpc_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_route53_resolver_rule_association.this.id
}

output "this" {
  value = aws_route53_resolver_rule_association.this
}
```

[top](#index)