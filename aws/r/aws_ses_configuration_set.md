# aws_ses_configuration_set

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
module "aws_ses_configuration_set" {
  source = "./modules/aws/r/aws_ses_configuration_set"

  # name - (required) is a type of string
  name = null

  delivery_options = [{
    tls_policy = null
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

variable "delivery_options" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      tls_policy = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_ses_configuration_set" "this" {
  name = var.name

  dynamic "delivery_options" {
    for_each = var.delivery_options
    content {
      tls_policy = delivery_options.value["tls_policy"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_ses_configuration_set.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_ses_configuration_set.this.id
}

output "this" {
  value = aws_ses_configuration_set.this
}
```

[top](#index)