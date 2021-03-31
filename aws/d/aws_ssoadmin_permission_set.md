# aws_ssoadmin_permission_set

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "aws_ssoadmin_permission_set" {
  source = "./modules/aws/d/aws_ssoadmin_permission_set"

  # arn - (optional) is a type of string
  arn = null
  # instance_arn - (required) is a type of string
  instance_arn = null
  # name - (optional) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_arn" {
  description = "(required)"
  type        = string
}

variable "name" {
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

### Datasource

```terraform
data "aws_ssoadmin_permission_set" "this" {
  arn          = var.arn
  instance_arn = var.instance_arn
  name         = var.name
  tags         = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = data.aws_ssoadmin_permission_set.this.arn
}

output "created_date" {
  description = "returns a string"
  value       = data.aws_ssoadmin_permission_set.this.created_date
}

output "description" {
  description = "returns a string"
  value       = data.aws_ssoadmin_permission_set.this.description
}

output "id" {
  description = "returns a string"
  value       = data.aws_ssoadmin_permission_set.this.id
}

output "name" {
  description = "returns a string"
  value       = data.aws_ssoadmin_permission_set.this.name
}

output "relay_state" {
  description = "returns a string"
  value       = data.aws_ssoadmin_permission_set.this.relay_state
}

output "session_duration" {
  description = "returns a string"
  value       = data.aws_ssoadmin_permission_set.this.session_duration
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_ssoadmin_permission_set.this.tags
}

output "this" {
  value = aws_ssoadmin_permission_set.this
}
```

[top](#index)