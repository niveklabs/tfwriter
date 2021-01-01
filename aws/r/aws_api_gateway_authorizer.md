# aws_api_gateway_authorizer

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "aws_api_gateway_authorizer" {
  source = "./modules/aws/r/aws_api_gateway_authorizer"

  # authorizer_credentials - (optional) is a type of string
  authorizer_credentials = null
  # authorizer_result_ttl_in_seconds - (optional) is a type of number
  authorizer_result_ttl_in_seconds = null
  # authorizer_uri - (optional) is a type of string
  authorizer_uri = null
  # identity_source - (optional) is a type of string
  identity_source = null
  # identity_validation_expression - (optional) is a type of string
  identity_validation_expression = null
  # name - (required) is a type of string
  name = null
  # provider_arns - (optional) is a type of set of string
  provider_arns = []
  # rest_api_id - (required) is a type of string
  rest_api_id = null
  # type - (optional) is a type of string
  type = null
}
```

[top](#index)

### Variables

```hcl
variable "authorizer_credentials" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "authorizer_result_ttl_in_seconds" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "authorizer_uri" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "identity_source" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "identity_validation_expression" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "provider_arns" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "rest_api_id" {
  description = "(required)"
  type        = string
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```hcl
resource "aws_api_gateway_authorizer" "this" {
  authorizer_credentials           = var.authorizer_credentials
  authorizer_result_ttl_in_seconds = var.authorizer_result_ttl_in_seconds
  authorizer_uri                   = var.authorizer_uri
  identity_source                  = var.identity_source
  identity_validation_expression   = var.identity_validation_expression
  name                             = var.name
  provider_arns                    = var.provider_arns
  rest_api_id                      = var.rest_api_id
  type                             = var.type
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_api_gateway_authorizer.this.id
}

output "this" {
  value = aws_api_gateway_authorizer.this
}
```

[top](#index)