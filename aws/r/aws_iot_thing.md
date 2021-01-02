# aws_iot_thing

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
module "aws_iot_thing" {
  source = "./modules/aws/r/aws_iot_thing"

  # attributes - (optional) is a type of map of string
  attributes = {}
  # name - (required) is a type of string
  name = null
  # thing_type_name - (optional) is a type of string
  thing_type_name = null
}
```

[top](#index)

### Variables

```terraform
variable "attributes" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "thing_type_name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_iot_thing" "this" {
  attributes      = var.attributes
  name            = var.name
  thing_type_name = var.thing_type_name
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_iot_thing.this.arn
}

output "default_client_id" {
  description = "returns a string"
  value       = aws_iot_thing.this.default_client_id
}

output "id" {
  description = "returns a string"
  value       = aws_iot_thing.this.id
}

output "version" {
  description = "returns a number"
  value       = aws_iot_thing.this.version
}

output "this" {
  value = aws_iot_thing.this
}
```

[top](#index)