# aws_api_gateway_account

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
module "aws_api_gateway_account" {
  source = "./modules/aws/r/aws_api_gateway_account"

  # cloudwatch_role_arn - (optional) is a type of string
  cloudwatch_role_arn = null
}
```

[top](#index)

### Variables

```terraform
variable "cloudwatch_role_arn" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_api_gateway_account" "this" {
  cloudwatch_role_arn = var.cloudwatch_role_arn
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_api_gateway_account.this.id
}

output "throttle_settings" {
  description = "returns a list of object"
  value       = aws_api_gateway_account.this.throttle_settings
}

output "this" {
  value = aws_api_gateway_account.this
}
```

[top](#index)