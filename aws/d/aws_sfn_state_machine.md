# aws_sfn_state_machine

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "aws_sfn_state_machine" {
  source = "./modules/aws/d/aws_sfn_state_machine"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```hcl
variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```hcl
data "aws_sfn_state_machine" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```hcl
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