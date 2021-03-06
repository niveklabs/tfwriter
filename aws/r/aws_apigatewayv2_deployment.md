# aws_apigatewayv2_deployment

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
module "aws_apigatewayv2_deployment" {
  source = "./modules/aws/r/aws_apigatewayv2_deployment"

  # api_id - (required) is a type of string
  api_id = null
  # description - (optional) is a type of string
  description = null
  # triggers - (optional) is a type of map of string
  triggers = {}
}
```

[top](#index)

### Variables

```terraform
variable "api_id" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "triggers" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_apigatewayv2_deployment" "this" {
  # api_id - (required) is a type of string
  api_id = var.api_id
  # description - (optional) is a type of string
  description = var.description
  # triggers - (optional) is a type of map of string
  triggers = var.triggers
}
```

[top](#index)

### Outputs

```terraform
output "auto_deployed" {
  description = "returns a bool"
  value       = aws_apigatewayv2_deployment.this.auto_deployed
}

output "id" {
  description = "returns a string"
  value       = aws_apigatewayv2_deployment.this.id
}

output "this" {
  value = aws_apigatewayv2_deployment.this
}
```

[top](#index)