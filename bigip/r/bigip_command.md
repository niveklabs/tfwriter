# bigip_command

[back](../bigip.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    bigip = ">= 1.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "bigip_command" {
  source = "./modules/bigip/r/bigip_command"

  # command_result - (optional) is a type of list of string
  command_result = []
  # commands - (required) is a type of list of string
  commands = []
  # when - (optional) is a type of string
  when = null
}
```

[top](#index)

### Variables

```terraform
variable "command_result" {
  description = "(optional) - Partition of ssl certificate"
  type        = list(string)
  default     = null
}

variable "commands" {
  description = "(required) - The commands to send to the remote BIG-IP device over the configured provider"
  type        = list(string)
}

variable "when" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "bigip_command" "this" {
  command_result = var.command_result
  commands       = var.commands
  when           = var.when
}
```

[top](#index)

### Outputs

```terraform
output "command_result" {
  description = "returns a list of string"
  value       = bigip_command.this.command_result
}

output "id" {
  description = "returns a string"
  value       = bigip_command.this.id
}

output "this" {
  value = bigip_command.this
}
```

[top](#index)