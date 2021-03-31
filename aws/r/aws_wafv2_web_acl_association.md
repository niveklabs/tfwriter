# aws_wafv2_web_acl_association

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
module "aws_wafv2_web_acl_association" {
  source = "./modules/aws/r/aws_wafv2_web_acl_association"

  # resource_arn - (required) is a type of string
  resource_arn = null
  # web_acl_arn - (required) is a type of string
  web_acl_arn = null
}
```

[top](#index)

### Variables

```terraform
variable "resource_arn" {
  description = "(required)"
  type        = string
}

variable "web_acl_arn" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_wafv2_web_acl_association" "this" {
  resource_arn = var.resource_arn
  web_acl_arn  = var.web_acl_arn
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_wafv2_web_acl_association.this.id
}

output "this" {
  value = aws_wafv2_web_acl_association.this
}
```

[top](#index)