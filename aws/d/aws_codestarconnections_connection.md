# aws_codestarconnections_connection

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
module "aws_codestarconnections_connection" {
  source = "./modules/aws/d/aws_codestarconnections_connection"

  # arn - (required) is a type of string
  arn = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "arn" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aws_codestarconnections_connection" "this" {
  arn  = var.arn
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "connection_status" {
  description = "returns a string"
  value       = data.aws_codestarconnections_connection.this.connection_status
}

output "id" {
  description = "returns a string"
  value       = data.aws_codestarconnections_connection.this.id
}

output "name" {
  description = "returns a string"
  value       = data.aws_codestarconnections_connection.this.name
}

output "provider_type" {
  description = "returns a string"
  value       = data.aws_codestarconnections_connection.this.provider_type
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_codestarconnections_connection.this.tags
}

output "this" {
  value = aws_codestarconnections_connection.this
}
```

[top](#index)