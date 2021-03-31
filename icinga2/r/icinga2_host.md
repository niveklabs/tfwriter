# icinga2_host

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
module "icinga2_host" {
  source = "./modules/icinga2/r/icinga2_host"

  # address - (required) is a type of string
  address = null
  # check_command - (required) is a type of string
  check_command = null
  # groups - (optional) is a type of list of string
  groups = []
  # hostname - (required) is a type of string
  hostname = null
  # templates - (optional) is a type of list of string
  templates = []
  # vars - (optional) is a type of map of string
  vars = {}
}
```

[top](#index)

### Variables

```terraform
variable "address" {
  description = "(required)"
  type        = string
}

variable "check_command" {
  description = "(required)"
  type        = string
}

variable "groups" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "hostname" {
  description = "(required) - Hostname"
  type        = string
}

variable "templates" {
  description = "(optional)"
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
resource "icinga2_host" "this" {
  address       = var.address
  check_command = var.check_command
  groups        = var.groups
  hostname      = var.hostname
  templates     = var.templates
  vars          = var.vars
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = icinga2_host.this.id
}

output "this" {
  value = icinga2_host.this
}
```

[top](#index)