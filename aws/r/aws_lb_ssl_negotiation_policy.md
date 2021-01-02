# aws_lb_ssl_negotiation_policy

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
module "aws_lb_ssl_negotiation_policy" {
  source = "./modules/aws/r/aws_lb_ssl_negotiation_policy"

  # lb_port - (required) is a type of number
  lb_port = null
  # load_balancer - (required) is a type of string
  load_balancer = null
  # name - (required) is a type of string
  name = null

  attribute = [{
    name  = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "lb_port" {
  description = "(required)"
  type        = number
}

variable "load_balancer" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "attribute" {
  description = "nested mode: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name  = string
      value = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_lb_ssl_negotiation_policy" "this" {
  lb_port       = var.lb_port
  load_balancer = var.load_balancer
  name          = var.name

  dynamic "attribute" {
    for_each = var.attribute
    content {
      name  = attribute.value["name"]
      value = attribute.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_lb_ssl_negotiation_policy.this.id
}

output "this" {
  value = aws_lb_ssl_negotiation_policy.this
}
```

[top](#index)