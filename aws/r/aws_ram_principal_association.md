# aws_ram_principal_association

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
module "aws_ram_principal_association" {
  source = "./modules/aws/r/aws_ram_principal_association"

  # principal - (required) is a type of string
  principal = null
  # resource_share_arn - (required) is a type of string
  resource_share_arn = null
}
```

[top](#index)

### Variables

```terraform
variable "principal" {
  description = "(required)"
  type        = string
}

variable "resource_share_arn" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_ram_principal_association" "this" {
  # principal - (required) is a type of string
  principal = var.principal
  # resource_share_arn - (required) is a type of string
  resource_share_arn = var.resource_share_arn
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_ram_principal_association.this.id
}

output "this" {
  value = aws_ram_principal_association.this
}
```

[top](#index)