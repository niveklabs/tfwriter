# aws_msk_configuration

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
module "aws_msk_configuration" {
  source = "./modules/aws/r/aws_msk_configuration"

  # description - (optional) is a type of string
  description = null
  # kafka_versions - (required) is a type of set of string
  kafka_versions = []
  # name - (required) is a type of string
  name = null
  # server_properties - (required) is a type of string
  server_properties = null
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

variable "kafka_versions" {
  description = "(required)"
  type        = set(string)
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "server_properties" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_msk_configuration" "this" {
  # description - (optional) is a type of string
  description = var.description
  # kafka_versions - (required) is a type of set of string
  kafka_versions = var.kafka_versions
  # name - (required) is a type of string
  name = var.name
  # server_properties - (required) is a type of string
  server_properties = var.server_properties
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_msk_configuration.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_msk_configuration.this.id
}

output "latest_revision" {
  description = "returns a number"
  value       = aws_msk_configuration.this.latest_revision
}

output "this" {
  value = aws_msk_configuration.this
}
```

[top](#index)