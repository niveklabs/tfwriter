# aws_api_gateway_resource

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
module "aws_api_gateway_resource" {
  source = "./modules/aws/r/aws_api_gateway_resource"

  # parent_id - (required) is a type of string
  parent_id = null
  # path_part - (required) is a type of string
  path_part = null
  # rest_api_id - (required) is a type of string
  rest_api_id = null
}
```

[top](#index)

### Variables

```terraform
variable "parent_id" {
  description = "(required)"
  type        = string
}

variable "path_part" {
  description = "(required)"
  type        = string
}

variable "rest_api_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_api_gateway_resource" "this" {
  parent_id   = var.parent_id
  path_part   = var.path_part
  rest_api_id = var.rest_api_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_api_gateway_resource.this.id
}

output "path" {
  description = "returns a string"
  value       = aws_api_gateway_resource.this.path
}

output "this" {
  value = aws_api_gateway_resource.this
}
```

[top](#index)