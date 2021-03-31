# aws_emr_security_configuration

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
module "aws_emr_security_configuration" {
  source = "./modules/aws/r/aws_emr_security_configuration"

  # configuration - (required) is a type of string
  configuration = null
  # name - (optional) is a type of string
  name = null
  # name_prefix - (optional) is a type of string
  name_prefix = null
}
```

[top](#index)

### Variables

```terraform
variable "configuration" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_emr_security_configuration" "this" {
  configuration = var.configuration
  name          = var.name
  name_prefix   = var.name_prefix
}
```

[top](#index)

### Outputs

```terraform
output "creation_date" {
  description = "returns a string"
  value       = aws_emr_security_configuration.this.creation_date
}

output "id" {
  description = "returns a string"
  value       = aws_emr_security_configuration.this.id
}

output "name" {
  description = "returns a string"
  value       = aws_emr_security_configuration.this.name
}

output "this" {
  value = aws_emr_security_configuration.this
}
```

[top](#index)