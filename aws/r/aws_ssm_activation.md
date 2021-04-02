# aws_ssm_activation

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
module "aws_ssm_activation" {
  source = "./modules/aws/r/aws_ssm_activation"

  # description - (optional) is a type of string
  description = null
  # expiration_date - (optional) is a type of string
  expiration_date = null
  # iam_role - (required) is a type of string
  iam_role = null
  # name - (optional) is a type of string
  name = null
  # registration_limit - (optional) is a type of number
  registration_limit = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "expiration_date" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "iam_role" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "registration_limit" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_ssm_activation" "this" {
  description        = var.description
  expiration_date    = var.expiration_date
  iam_role           = var.iam_role
  name               = var.name
  registration_limit = var.registration_limit
  tags               = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "activation_code" {
  description = "returns a string"
  value       = aws_ssm_activation.this.activation_code
}

output "expiration_date" {
  description = "returns a string"
  value       = aws_ssm_activation.this.expiration_date
}

output "expired" {
  description = "returns a bool"
  value       = aws_ssm_activation.this.expired
}

output "id" {
  description = "returns a string"
  value       = aws_ssm_activation.this.id
}

output "registration_count" {
  description = "returns a number"
  value       = aws_ssm_activation.this.registration_count
}

output "this" {
  value = aws_ssm_activation.this
}
```

[top](#index)