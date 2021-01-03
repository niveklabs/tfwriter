# fortios_sshfilter_profile

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_sshfilter_profile" {
  source = "./modules/fortios/r/fortios_sshfilter_profile"

  # block - (optional) is a type of string
  block = null
  # default_command_log - (optional) is a type of string
  default_command_log = null
  # log - (optional) is a type of string
  log = null
  # name - (optional) is a type of string
  name = null

  shell_commands = [{
    action   = null
    alert    = null
    id       = null
    log      = null
    pattern  = null
    severity = null
    type     = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "block" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_command_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "shell_commands" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action   = string
      alert    = string
      id       = number
      log      = string
      pattern  = string
      severity = string
      type     = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_sshfilter_profile" "this" {
  block               = var.block
  default_command_log = var.default_command_log
  log                 = var.log
  name                = var.name

  dynamic "shell_commands" {
    for_each = var.shell_commands
    content {
      action   = shell_commands.value["action"]
      alert    = shell_commands.value["alert"]
      id       = shell_commands.value["id"]
      log      = shell_commands.value["log"]
      pattern  = shell_commands.value["pattern"]
      severity = shell_commands.value["severity"]
      type     = shell_commands.value["type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "block" {
  description = "returns a string"
  value       = fortios_sshfilter_profile.this.block
}

output "default_command_log" {
  description = "returns a string"
  value       = fortios_sshfilter_profile.this.default_command_log
}

output "id" {
  description = "returns a string"
  value       = fortios_sshfilter_profile.this.id
}

output "log" {
  description = "returns a string"
  value       = fortios_sshfilter_profile.this.log
}

output "name" {
  description = "returns a string"
  value       = fortios_sshfilter_profile.this.name
}

output "this" {
  value = fortios_sshfilter_profile.this
}
```

[top](#index)