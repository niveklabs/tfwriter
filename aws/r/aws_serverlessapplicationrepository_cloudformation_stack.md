# aws_serverlessapplicationrepository_cloudformation_stack

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
module "aws_serverlessapplicationrepository_cloudformation_stack" {
  source = "./modules/aws/r/aws_serverlessapplicationrepository_cloudformation_stack"

  # application_id - (required) is a type of string
  application_id = null
  # capabilities - (required) is a type of set of string
  capabilities = []
  # name - (required) is a type of string
  name = null
  # parameters - (optional) is a type of map of string
  parameters = {}
  # semantic_version - (optional) is a type of string
  semantic_version = null
  # tags - (optional) is a type of map of string
  tags = {}

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "application_id" {
  description = "(required)"
  type        = string
}

variable "capabilities" {
  description = "(required)"
  type        = set(string)
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "parameters" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "semantic_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_serverlessapplicationrepository_cloudformation_stack" "this" {
  application_id   = var.application_id
  capabilities     = var.capabilities
  name             = var.name
  parameters       = var.parameters
  semantic_version = var.semantic_version
  tags             = var.tags

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_serverlessapplicationrepository_cloudformation_stack.this.id
}

output "outputs" {
  description = "returns a map of string"
  value       = aws_serverlessapplicationrepository_cloudformation_stack.this.outputs
}

output "parameters" {
  description = "returns a map of string"
  value       = aws_serverlessapplicationrepository_cloudformation_stack.this.parameters
}

output "semantic_version" {
  description = "returns a string"
  value       = aws_serverlessapplicationrepository_cloudformation_stack.this.semantic_version
}

output "this" {
  value = aws_serverlessapplicationrepository_cloudformation_stack.this
}
```

[top](#index)