# aws_ssoadmin_permission_set

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
module "aws_ssoadmin_permission_set" {
  source = "./modules/aws/r/aws_ssoadmin_permission_set"

  # description - (optional) is a type of string
  description = null
  # instance_arn - (required) is a type of string
  instance_arn = null
  # name - (required) is a type of string
  name = null
  # relay_state - (optional) is a type of string
  relay_state = null
  # session_duration - (optional) is a type of string
  session_duration = null
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

variable "instance_arn" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "relay_state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "session_duration" {
  description = "(optional)"
  type        = string
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
resource "aws_ssoadmin_permission_set" "this" {
  # description - (optional) is a type of string
  description = var.description
  # instance_arn - (required) is a type of string
  instance_arn = var.instance_arn
  # name - (required) is a type of string
  name = var.name
  # relay_state - (optional) is a type of string
  relay_state = var.relay_state
  # session_duration - (optional) is a type of string
  session_duration = var.session_duration
  # tags - (optional) is a type of map of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_ssoadmin_permission_set.this.arn
}

output "created_date" {
  description = "returns a string"
  value       = aws_ssoadmin_permission_set.this.created_date
}

output "id" {
  description = "returns a string"
  value       = aws_ssoadmin_permission_set.this.id
}

output "this" {
  value = aws_ssoadmin_permission_set.this
}
```

[top](#index)