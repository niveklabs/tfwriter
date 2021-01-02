# aws_api_gateway_deployment

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
module "aws_api_gateway_deployment" {
  source = "./modules/aws/r/aws_api_gateway_deployment"

  # description - (optional) is a type of string
  description = null
  # rest_api_id - (required) is a type of string
  rest_api_id = null
  # stage_description - (optional) is a type of string
  stage_description = null
  # stage_name - (optional) is a type of string
  stage_name = null
  # triggers - (optional) is a type of map of string
  triggers = {}
  # variables - (optional) is a type of map of string
  variables = {}
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

variable "rest_api_id" {
  description = "(required)"
  type        = string
}

variable "stage_description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "stage_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "triggers" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "variables" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_api_gateway_deployment" "this" {
  description       = var.description
  rest_api_id       = var.rest_api_id
  stage_description = var.stage_description
  stage_name        = var.stage_name
  triggers          = var.triggers
  variables         = var.variables
}
```

[top](#index)

### Outputs

```terraform
output "created_date" {
  description = "returns a string"
  value       = aws_api_gateway_deployment.this.created_date
}

output "execution_arn" {
  description = "returns a string"
  value       = aws_api_gateway_deployment.this.execution_arn
}

output "id" {
  description = "returns a string"
  value       = aws_api_gateway_deployment.this.id
}

output "invoke_url" {
  description = "returns a string"
  value       = aws_api_gateway_deployment.this.invoke_url
}

output "this" {
  value = aws_api_gateway_deployment.this
}
```

[top](#index)