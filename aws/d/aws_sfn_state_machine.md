# aws_sfn_state_machine

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
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_sfn_state_machine" {
  source = "./modules/aws/d/aws_sfn_state_machine"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "aws_sfn_state_machine" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = data.aws_sfn_state_machine.this.arn
}

output "creation_date" {
  description = "returns a string"
  value       = data.aws_sfn_state_machine.this.creation_date
}

output "definition" {
  description = "returns a string"
  value       = data.aws_sfn_state_machine.this.definition
}

output "id" {
  description = "returns a string"
  value       = data.aws_sfn_state_machine.this.id
}

output "role_arn" {
  description = "returns a string"
  value       = data.aws_sfn_state_machine.this.role_arn
}

output "status" {
  description = "returns a string"
  value       = data.aws_sfn_state_machine.this.status
}

output "this" {
  value = aws_sfn_state_machine.this
}
```

[top](#index)