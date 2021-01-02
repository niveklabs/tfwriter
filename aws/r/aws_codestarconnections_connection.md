# aws_codestarconnections_connection

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
module "aws_codestarconnections_connection" {
  source = "./modules/aws/r/aws_codestarconnections_connection"

  # name - (required) is a type of string
  name = null
  # provider_type - (required) is a type of string
  provider_type = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "provider_type" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_codestarconnections_connection" "this" {
  name          = var.name
  provider_type = var.provider_type
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_codestarconnections_connection.this.arn
}

output "connection_status" {
  description = "returns a string"
  value       = aws_codestarconnections_connection.this.connection_status
}

output "id" {
  description = "returns a string"
  value       = aws_codestarconnections_connection.this.id
}

output "this" {
  value = aws_codestarconnections_connection.this
}
```

[top](#index)