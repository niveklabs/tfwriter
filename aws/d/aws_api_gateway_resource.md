# aws_api_gateway_resource

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
module "aws_api_gateway_resource" {
  source = "./modules/aws/d/aws_api_gateway_resource"

  # path - (required) is a type of string
  path = null
  # rest_api_id - (required) is a type of string
  rest_api_id = null
}
```

[top](#index)

### Variables

```terraform
variable "path" {
  description = "(required)"
  type        = string
}

variable "rest_api_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "aws_api_gateway_resource" "this" {
  path        = var.path
  rest_api_id = var.rest_api_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.aws_api_gateway_resource.this.id
}

output "parent_id" {
  description = "returns a string"
  value       = data.aws_api_gateway_resource.this.parent_id
}

output "path_part" {
  description = "returns a string"
  value       = data.aws_api_gateway_resource.this.path_part
}

output "this" {
  value = aws_api_gateway_resource.this
}
```

[top](#index)