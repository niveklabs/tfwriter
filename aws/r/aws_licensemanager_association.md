# aws_licensemanager_association

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
module "aws_licensemanager_association" {
  source = "./modules/aws/r/aws_licensemanager_association"

  # license_configuration_arn - (required) is a type of string
  license_configuration_arn = null
  # resource_arn - (required) is a type of string
  resource_arn = null
}
```

[top](#index)

### Variables

```terraform
variable "license_configuration_arn" {
  description = "(required)"
  type        = string
}

variable "resource_arn" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_licensemanager_association" "this" {
  license_configuration_arn = var.license_configuration_arn
  resource_arn              = var.resource_arn
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_licensemanager_association.this.id
}

output "this" {
  value = aws_licensemanager_association.this
}
```

[top](#index)