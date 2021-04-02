# aws_apigatewayv2_apis

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
module "aws_apigatewayv2_apis" {
  source = "./modules/aws/d/aws_apigatewayv2_apis"

  # name - (optional) is a type of string
  name = null
  # protocol_type - (optional) is a type of string
  protocol_type = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "protocol_type" {
  description = "(optional)"
  type        = string
  default     = null
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
data "aws_apigatewayv2_apis" "this" {
  name          = var.name
  protocol_type = var.protocol_type
  tags          = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.aws_apigatewayv2_apis.this.id
}

output "ids" {
  description = "returns a set of string"
  value       = data.aws_apigatewayv2_apis.this.ids
}

output "this" {
  value = aws_apigatewayv2_apis.this
}
```

[top](#index)