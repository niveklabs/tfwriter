# aws_glacier_vault

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
module "aws_glacier_vault" {
  source = "./modules/aws/r/aws_glacier_vault"

  # access_policy - (optional) is a type of string
  access_policy = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}

  notification = [{
    events    = []
    sns_topic = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "access_policy" {
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

variable "notification" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      events    = set(string)
      sns_topic = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_glacier_vault" "this" {
  access_policy = var.access_policy
  name          = var.name
  tags          = var.tags

  dynamic "notification" {
    for_each = var.notification
    content {
      events    = notification.value["events"]
      sns_topic = notification.value["sns_topic"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_glacier_vault.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_glacier_vault.this.id
}

output "location" {
  description = "returns a string"
  value       = aws_glacier_vault.this.location
}

output "this" {
  value = aws_glacier_vault.this
}
```

[top](#index)