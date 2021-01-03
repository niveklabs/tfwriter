# icinga2_checkcommand

[back](../icinga2.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    icinga2 = ">= 0.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "icinga2_checkcommand" {
  source = "./modules/icinga2/r/icinga2_checkcommand"

  # arguments - (optional) is a type of map of string
  arguments = {}
  # command - (required) is a type of string
  command = null
  # name - (required) is a type of string
  name = null
  # templates - (required) is a type of list of string
  templates = []
}
```

[top](#index)

### Variables

```terraform
variable "arguments" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "command" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required) - Name"
  type        = string
}

variable "templates" {
  description = "(required)"
  type        = list(string)
}
```

[top](#index)

### Resource

```terraform
resource "icinga2_checkcommand" "this" {
  arguments = var.arguments
  command   = var.command
  name      = var.name
  templates = var.templates
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = icinga2_checkcommand.this.id
}

output "this" {
  value = icinga2_checkcommand.this
}
```

[top](#index)