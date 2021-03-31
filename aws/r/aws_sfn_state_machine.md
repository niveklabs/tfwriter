# aws_sfn_state_machine

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
module "aws_sfn_state_machine" {
  source = "./modules/aws/r/aws_sfn_state_machine"

  # definition - (required) is a type of string
  definition = null
  # name - (required) is a type of string
  name = null
  # role_arn - (required) is a type of string
  role_arn = null
  # tags - (optional) is a type of map of string
  tags = {}
  # type - (optional) is a type of string
  type = null

  logging_configuration = [{
    include_execution_data = null
    level                  = null
    log_destination        = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "definition" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "role_arn" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "logging_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      include_execution_data = bool
      level                  = string
      log_destination        = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_sfn_state_machine" "this" {
  definition = var.definition
  name       = var.name
  role_arn   = var.role_arn
  tags       = var.tags
  type       = var.type

  dynamic "logging_configuration" {
    for_each = var.logging_configuration
    content {
      include_execution_data = logging_configuration.value["include_execution_data"]
      level                  = logging_configuration.value["level"]
      log_destination        = logging_configuration.value["log_destination"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_sfn_state_machine.this.arn
}

output "creation_date" {
  description = "returns a string"
  value       = aws_sfn_state_machine.this.creation_date
}

output "id" {
  description = "returns a string"
  value       = aws_sfn_state_machine.this.id
}

output "status" {
  description = "returns a string"
  value       = aws_sfn_state_machine.this.status
}

output "this" {
  value = aws_sfn_state_machine.this
}
```

[top](#index)