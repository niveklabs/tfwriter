# alicloud_ecs_commands

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_ecs_commands" {
  source = "./modules/alicloud/d/alicloud_ecs_commands"

  # command_provider - (optional) is a type of string
  command_provider = null
  # content_encoding - (optional) is a type of string
  content_encoding = null
  # description - (optional) is a type of string
  description = null
  # ids - (optional) is a type of list of string
  ids = []
  # name - (optional) is a type of string
  name = null
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # type - (optional) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "command_provider" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "content_encoding" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_ecs_commands" "this" {
  command_provider = var.command_provider
  content_encoding = var.content_encoding
  description      = var.description
  ids              = var.ids
  name             = var.name
  name_regex       = var.name_regex
  output_file      = var.output_file
  type             = var.type
}
```

[top](#index)

### Outputs

```terraform
output "commands" {
  description = "returns a list of object"
  value       = data.alicloud_ecs_commands.this.commands
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_ecs_commands.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_ecs_commands.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_ecs_commands.this.names
}

output "this" {
  value = alicloud_ecs_commands.this
}
```

[top](#index)