# icinga2_service

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
    icinga2 = ">= 0.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "icinga2_service" {
  source = "./modules/icinga2/r/icinga2_service"

  # check_command - (required) is a type of string
  check_command = null
  # hostname - (required) is a type of string
  hostname = null
  # name - (required) is a type of string
  name = null
  # templates - (optional) is a type of list of string
  templates = []
  # vars - (optional) is a type of map of string
  vars = {}
}
```

[top](#index)

### Variables

```terraform
variable "check_command" {
  description = "(required) - CheckCommand"
  type        = string
}

variable "hostname" {
  description = "(required) - Hostname"
  type        = string
}

variable "name" {
  description = "(required) - ServiceName"
  type        = string
}

variable "templates" {
  description = "(optional) - Templates"
  type        = list(string)
  default     = null
}

variable "vars" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "icinga2_service" "this" {
  # check_command - (required) is a type of string
  check_command = var.check_command
  # hostname - (required) is a type of string
  hostname = var.hostname
  # name - (required) is a type of string
  name = var.name
  # templates - (optional) is a type of list of string
  templates = var.templates
  # vars - (optional) is a type of map of string
  vars = var.vars
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = icinga2_service.this.id
}

output "this" {
  value = icinga2_service.this
}
```

[top](#index)