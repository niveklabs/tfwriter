# aws_api_gateway_vpc_link

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
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_api_gateway_vpc_link" {
  source = "./modules/aws/d/aws_api_gateway_vpc_link"

  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "name" {
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
data "aws_api_gateway_vpc_link" "this" {
  # name - (required) is a type of string
  name = var.name
  # tags - (optional) is a type of map of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.aws_api_gateway_vpc_link.this.description
}

output "id" {
  description = "returns a string"
  value       = data.aws_api_gateway_vpc_link.this.id
}

output "status" {
  description = "returns a string"
  value       = data.aws_api_gateway_vpc_link.this.status
}

output "status_message" {
  description = "returns a string"
  value       = data.aws_api_gateway_vpc_link.this.status_message
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_api_gateway_vpc_link.this.tags
}

output "target_arns" {
  description = "returns a set of string"
  value       = data.aws_api_gateway_vpc_link.this.target_arns
}

output "this" {
  value = aws_api_gateway_vpc_link.this
}
```

[top](#index)