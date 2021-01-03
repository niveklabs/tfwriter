# icinga2_notification

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
module "icinga2_notification" {
  source = "./modules/icinga2/r/icinga2_notification"

  # command - (required) is a type of string
  command = null
  # hostname - (required) is a type of string
  hostname = null
  # interval - (optional) is a type of number
  interval = null
  # servicename - (optional) is a type of string
  servicename = null
  # templates - (optional) is a type of list of string
  templates = []
  # users - (optional) is a type of list of string
  users = []
  # vars - (optional) is a type of map of string
  vars = {}
}
```

[top](#index)

### Variables

```terraform
variable "command" {
  description = "(required)"
  type        = string
}

variable "hostname" {
  description = "(required)"
  type        = string
}

variable "interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "servicename" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "templates" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "users" {
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
resource "icinga2_notification" "this" {
  command     = var.command
  hostname    = var.hostname
  interval    = var.interval
  servicename = var.servicename
  templates   = var.templates
  users       = var.users
  vars        = var.vars
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = icinga2_notification.this.id
}

output "this" {
  value = icinga2_notification.this
}
```

[top](#index)