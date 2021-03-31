# aws_transfer_server

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
module "aws_transfer_server" {
  source = "./modules/aws/d/aws_transfer_server"

  # server_id - (required) is a type of string
  server_id = null
}
```

[top](#index)

### Variables

```terraform
variable "server_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "aws_transfer_server" "this" {
  server_id = var.server_id
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = data.aws_transfer_server.this.arn
}

output "endpoint" {
  description = "returns a string"
  value       = data.aws_transfer_server.this.endpoint
}

output "id" {
  description = "returns a string"
  value       = data.aws_transfer_server.this.id
}

output "identity_provider_type" {
  description = "returns a string"
  value       = data.aws_transfer_server.this.identity_provider_type
}

output "invocation_role" {
  description = "returns a string"
  value       = data.aws_transfer_server.this.invocation_role
}

output "logging_role" {
  description = "returns a string"
  value       = data.aws_transfer_server.this.logging_role
}

output "url" {
  description = "returns a string"
  value       = data.aws_transfer_server.this.url
}

output "this" {
  value = aws_transfer_server.this
}
```

[top](#index)