# aws_api_gateway_rest_api_policy

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
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_api_gateway_rest_api_policy" {
  source = "./modules/aws/r/aws_api_gateway_rest_api_policy"

  # policy - (required) is a type of string
  policy = null
  # rest_api_id - (required) is a type of string
  rest_api_id = null
}
```

[top](#index)

### Variables

```terraform
variable "policy" {
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
resource "aws_api_gateway_rest_api_policy" "this" {
  policy      = var.policy
  rest_api_id = var.rest_api_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_api_gateway_rest_api_policy.this.id
}

output "this" {
  value = aws_api_gateway_rest_api_policy.this
}
```

[top](#index)