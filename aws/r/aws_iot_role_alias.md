# aws_iot_role_alias

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
module "aws_iot_role_alias" {
  source = "./modules/aws/r/aws_iot_role_alias"

  # alias - (required) is a type of string
  alias = null
  # credential_duration - (optional) is a type of number
  credential_duration = null
  # role_arn - (required) is a type of string
  role_arn = null
}
```

[top](#index)

### Variables

```terraform
variable "alias" {
  description = "(required)"
  type        = string
}

variable "credential_duration" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "role_arn" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_iot_role_alias" "this" {
  alias               = var.alias
  credential_duration = var.credential_duration
  role_arn            = var.role_arn
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_iot_role_alias.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_iot_role_alias.this.id
}

output "this" {
  value = aws_iot_role_alias.this
}
```

[top](#index)