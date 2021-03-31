# aws_msk_configuration

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "aws_msk_configuration" {
  source = "./modules/aws/d/aws_msk_configuration"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "aws_msk_configuration" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = data.aws_msk_configuration.this.arn
}

output "description" {
  description = "returns a string"
  value       = data.aws_msk_configuration.this.description
}

output "id" {
  description = "returns a string"
  value       = data.aws_msk_configuration.this.id
}

output "kafka_versions" {
  description = "returns a set of string"
  value       = data.aws_msk_configuration.this.kafka_versions
}

output "latest_revision" {
  description = "returns a number"
  value       = data.aws_msk_configuration.this.latest_revision
}

output "server_properties" {
  description = "returns a string"
  value       = data.aws_msk_configuration.this.server_properties
}

output "this" {
  value = aws_msk_configuration.this
}
```

[top](#index)