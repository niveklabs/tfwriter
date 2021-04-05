# alicloud_ecs_command

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_ecs_command" {
  source = "./modules/alicloud/r/alicloud_ecs_command"

  # command_content - (required) is a type of string
  command_content = null
  # description - (optional) is a type of string
  description = null
  # enable_parameter - (optional) is a type of bool
  enable_parameter = null
  # name - (required) is a type of string
  name = null
  # timeout - (optional) is a type of number
  timeout = null
  # type - (required) is a type of string
  type = null
  # working_dir - (optional) is a type of string
  working_dir = null
}
```

[top](#index)

### Variables

```terraform
variable "command_content" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable_parameter" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "working_dir" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_ecs_command" "this" {
  command_content  = var.command_content
  description      = var.description
  enable_parameter = var.enable_parameter
  name             = var.name
  timeout          = var.timeout
  type             = var.type
  working_dir      = var.working_dir
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_ecs_command.this.id
}

output "this" {
  value = alicloud_ecs_command.this
}
```

[top](#index)