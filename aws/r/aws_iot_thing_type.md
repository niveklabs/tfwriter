# aws_iot_thing_type

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
module "aws_iot_thing_type" {
  source = "./modules/aws/r/aws_iot_thing_type"

  # deprecated - (optional) is a type of bool
  deprecated = null
  # name - (required) is a type of string
  name = null

  properties = [{
    description           = null
    searchable_attributes = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "deprecated" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "properties" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      description           = string
      searchable_attributes = set(string)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_iot_thing_type" "this" {
  deprecated = var.deprecated
  name       = var.name

  dynamic "properties" {
    for_each = var.properties
    content {
      description           = properties.value["description"]
      searchable_attributes = properties.value["searchable_attributes"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_iot_thing_type.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_iot_thing_type.this.id
}

output "this" {
  value = aws_iot_thing_type.this
}
```

[top](#index)