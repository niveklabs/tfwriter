# aws_guardduty_organization_configuration

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
module "aws_guardduty_organization_configuration" {
  source = "./modules/aws/r/aws_guardduty_organization_configuration"

  # auto_enable - (required) is a type of bool
  auto_enable = null
  # detector_id - (required) is a type of string
  detector_id = null
}
```

[top](#index)

### Variables

```terraform
variable "auto_enable" {
  description = "(required)"
  type        = bool
}

variable "detector_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_guardduty_organization_configuration" "this" {
  auto_enable = var.auto_enable
  detector_id = var.detector_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_guardduty_organization_configuration.this.id
}

output "this" {
  value = aws_guardduty_organization_configuration.this
}
```

[top](#index)