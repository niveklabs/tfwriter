# fortios_systemreplacemsg_trafficquota

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
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_systemreplacemsg_trafficquota" {
  source = "./modules/fortios/r/fortios_systemreplacemsg_trafficquota"

  # buffer - (optional) is a type of string
  buffer = null
  # format - (optional) is a type of string
  format = null
  # header - (optional) is a type of string
  header = null
  # msg_type - (required) is a type of string
  msg_type = null
}
```

[top](#index)

### Variables

```terraform
variable "buffer" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "format" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "header" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "msg_type" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "fortios_systemreplacemsg_trafficquota" "this" {
  # buffer - (optional) is a type of string
  buffer = var.buffer
  # format - (optional) is a type of string
  format = var.format
  # header - (optional) is a type of string
  header = var.header
  # msg_type - (required) is a type of string
  msg_type = var.msg_type
}
```

[top](#index)

### Outputs

```terraform
output "format" {
  description = "returns a string"
  value       = fortios_systemreplacemsg_trafficquota.this.format
}

output "header" {
  description = "returns a string"
  value       = fortios_systemreplacemsg_trafficquota.this.header
}

output "id" {
  description = "returns a string"
  value       = fortios_systemreplacemsg_trafficquota.this.id
}

output "this" {
  value = fortios_systemreplacemsg_trafficquota.this
}
```

[top](#index)