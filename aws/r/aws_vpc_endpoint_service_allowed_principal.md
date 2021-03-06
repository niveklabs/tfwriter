# aws_vpc_endpoint_service_allowed_principal

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
module "aws_vpc_endpoint_service_allowed_principal" {
  source = "./modules/aws/r/aws_vpc_endpoint_service_allowed_principal"

  # principal_arn - (required) is a type of string
  principal_arn = null
  # vpc_endpoint_service_id - (required) is a type of string
  vpc_endpoint_service_id = null
}
```

[top](#index)

### Variables

```terraform
variable "principal_arn" {
  description = "(required)"
  type        = string
}

variable "vpc_endpoint_service_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_vpc_endpoint_service_allowed_principal" "this" {
  # principal_arn - (required) is a type of string
  principal_arn = var.principal_arn
  # vpc_endpoint_service_id - (required) is a type of string
  vpc_endpoint_service_id = var.vpc_endpoint_service_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_vpc_endpoint_service_allowed_principal.this.id
}

output "this" {
  value = aws_vpc_endpoint_service_allowed_principal.this
}
```

[top](#index)