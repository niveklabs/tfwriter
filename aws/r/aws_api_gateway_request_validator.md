# aws_api_gateway_request_validator

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "aws_api_gateway_request_validator" {
  source = "./modules/aws/r/aws_api_gateway_request_validator"

  # name - (required) is a type of string
  name = null
  # rest_api_id - (required) is a type of string
  rest_api_id = null
  # validate_request_body - (optional) is a type of bool
  validate_request_body = null
  # validate_request_parameters - (optional) is a type of bool
  validate_request_parameters = null
}
```

[top](#index)

### Variables

```hcl
variable "name" {
  description = "(required)"
  type        = string
}

variable "rest_api_id" {
  description = "(required)"
  type        = string
}

variable "validate_request_body" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "validate_request_parameters" {
  description = "(optional)"
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```hcl
resource "aws_api_gateway_request_validator" "this" {
  name                        = var.name
  rest_api_id                 = var.rest_api_id
  validate_request_body       = var.validate_request_body
  validate_request_parameters = var.validate_request_parameters
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_api_gateway_request_validator.this.id
}

output "this" {
  value = aws_api_gateway_request_validator.this
}
```

[top](#index)