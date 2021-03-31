# aws_wafregional_ipset

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
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_wafregional_ipset" {
  source = "./modules/aws/r/aws_wafregional_ipset"

  # name - (required) is a type of string
  name = null

  ip_set_descriptor = [{
    type  = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "ip_set_descriptor" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      type  = string
      value = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_wafregional_ipset" "this" {
  name = var.name

  dynamic "ip_set_descriptor" {
    for_each = var.ip_set_descriptor
    content {
      type  = ip_set_descriptor.value["type"]
      value = ip_set_descriptor.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_wafregional_ipset.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_wafregional_ipset.this.id
}

output "this" {
  value = aws_wafregional_ipset.this
}
```

[top](#index)