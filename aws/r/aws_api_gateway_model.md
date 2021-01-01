# aws_api_gateway_model

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
module "aws_api_gateway_model" {
  source = "./modules/aws/r/aws_api_gateway_model"

  # content_type - (required) is a type of string
  content_type = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # rest_api_id - (required) is a type of string
  rest_api_id = null
  # schema - (optional) is a type of string
  schema = null
}
```

[top](#index)

### Variables

```hcl
variable "content_type" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "rest_api_id" {
  description = "(required)"
  type        = string
}

variable "schema" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```hcl
resource "aws_api_gateway_model" "this" {
  content_type = var.content_type
  description  = var.description
  name         = var.name
  rest_api_id  = var.rest_api_id
  schema       = var.schema
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_api_gateway_model.this.id
}

output "this" {
  value = aws_api_gateway_model.this
}
```

[top](#index)