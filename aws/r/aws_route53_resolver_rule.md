# aws_route53_resolver_rule

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
module "aws_route53_resolver_rule" {
  source = "./modules/aws/r/aws_route53_resolver_rule"

  # domain_name - (required) is a type of string
  domain_name = null
  # name - (optional) is a type of string
  name = null
  # resolver_endpoint_id - (optional) is a type of string
  resolver_endpoint_id = null
  # rule_type - (required) is a type of string
  rule_type = null
  # tags - (optional) is a type of map of string
  tags = {}

  target_ip = [{
    ip   = null
    port = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "domain_name" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resolver_endpoint_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rule_type" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "target_ip" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      ip   = string
      port = number
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_route53_resolver_rule" "this" {
  # domain_name - (required) is a type of string
  domain_name = var.domain_name
  # name - (optional) is a type of string
  name = var.name
  # resolver_endpoint_id - (optional) is a type of string
  resolver_endpoint_id = var.resolver_endpoint_id
  # rule_type - (required) is a type of string
  rule_type = var.rule_type
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "target_ip" {
    for_each = var.target_ip
    content {
      # ip - (required) is a type of string
      ip = target_ip.value["ip"]
      # port - (optional) is a type of number
      port = target_ip.value["port"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_route53_resolver_rule.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_route53_resolver_rule.this.id
}

output "owner_id" {
  description = "returns a string"
  value       = aws_route53_resolver_rule.this.owner_id
}

output "share_status" {
  description = "returns a string"
  value       = aws_route53_resolver_rule.this.share_status
}

output "this" {
  value = aws_route53_resolver_rule.this
}
```

[top](#index)