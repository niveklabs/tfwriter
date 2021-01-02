# aws_route53_resolver_endpoint

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
module "aws_route53_resolver_endpoint" {
  source = "./modules/aws/r/aws_route53_resolver_endpoint"

  # direction - (required) is a type of string
  direction = null
  # name - (optional) is a type of string
  name = null
  # security_group_ids - (required) is a type of set of string
  security_group_ids = []
  # tags - (optional) is a type of map of string
  tags = {}

  ip_address = [{
    ip        = null
    ip_id     = null
    subnet_id = null
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
variable "direction" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_group_ids" {
  description = "(required)"
  type        = set(string)
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "ip_address" {
  description = "nested mode: NestingSet, min items: 2, max items: 10"
  type = set(object(
    {
      ip        = string
      ip_id     = string
      subnet_id = string
    }
  ))
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
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
resource "aws_route53_resolver_endpoint" "this" {
  direction          = var.direction
  name               = var.name
  security_group_ids = var.security_group_ids
  tags               = var.tags

  dynamic "ip_address" {
    for_each = var.ip_address
    content {
      ip        = ip_address.value["ip"]
      subnet_id = ip_address.value["subnet_id"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
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
  value       = aws_route53_resolver_endpoint.this.arn
}

output "host_vpc_id" {
  description = "returns a string"
  value       = aws_route53_resolver_endpoint.this.host_vpc_id
}

output "id" {
  description = "returns a string"
  value       = aws_route53_resolver_endpoint.this.id
}

output "this" {
  value = aws_route53_resolver_endpoint.this
}
```

[top](#index)