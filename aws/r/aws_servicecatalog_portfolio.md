# aws_servicecatalog_portfolio

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
module "aws_servicecatalog_portfolio" {
  source = "./modules/aws/r/aws_servicecatalog_portfolio"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # provider_name - (optional) is a type of string
  provider_name = null
  # tags - (optional) is a type of map of string
  tags = {}

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
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "provider_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
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
resource "aws_servicecatalog_portfolio" "this" {
  description   = var.description
  name          = var.name
  provider_name = var.provider_name
  tags          = var.tags

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
  value       = aws_servicecatalog_portfolio.this.arn
}

output "created_time" {
  description = "returns a string"
  value       = aws_servicecatalog_portfolio.this.created_time
}

output "description" {
  description = "returns a string"
  value       = aws_servicecatalog_portfolio.this.description
}

output "id" {
  description = "returns a string"
  value       = aws_servicecatalog_portfolio.this.id
}

output "this" {
  value = aws_servicecatalog_portfolio.this
}
```

[top](#index)