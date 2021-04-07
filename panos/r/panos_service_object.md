# panos_service_object

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    panos = ">= 1.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_service_object" {
  source = "./modules/panos/r/panos_service_object"

  # description - (optional) is a type of string
  description = null
  # destination_port - (required) is a type of string
  destination_port = null
  # name - (required) is a type of string
  name = null
  # override_half_closed_timeout - (optional) is a type of number
  override_half_closed_timeout = null
  # override_session_timeout - (optional) is a type of bool
  override_session_timeout = null
  # override_time_wait_timeout - (optional) is a type of number
  override_time_wait_timeout = null
  # override_timeout - (optional) is a type of number
  override_timeout = null
  # protocol - (required) is a type of string
  protocol = null
  # source_port - (optional) is a type of string
  source_port = null
  # tags - (optional) is a type of list of string
  tags = []
  # vsys - (optional) is a type of string
  vsys = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Object's description"
  type        = string
  default     = null
}

variable "destination_port" {
  description = "(required) - The destination port definition"
  type        = string
}

variable "name" {
  description = "(required) - The service object's name"
  type        = string
}

variable "override_half_closed_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "override_session_timeout" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "override_time_wait_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "override_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "protocol" {
  description = "(required)"
  type        = string
}

variable "source_port" {
  description = "(optional) - The source port definition"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "vsys" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "panos_service_object" "this" {
  # description - (optional) is a type of string
  description = var.description
  # destination_port - (required) is a type of string
  destination_port = var.destination_port
  # name - (required) is a type of string
  name = var.name
  # override_half_closed_timeout - (optional) is a type of number
  override_half_closed_timeout = var.override_half_closed_timeout
  # override_session_timeout - (optional) is a type of bool
  override_session_timeout = var.override_session_timeout
  # override_time_wait_timeout - (optional) is a type of number
  override_time_wait_timeout = var.override_time_wait_timeout
  # override_timeout - (optional) is a type of number
  override_timeout = var.override_timeout
  # protocol - (required) is a type of string
  protocol = var.protocol
  # source_port - (optional) is a type of string
  source_port = var.source_port
  # tags - (optional) is a type of list of string
  tags = var.tags
  # vsys - (optional) is a type of string
  vsys = var.vsys
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_service_object.this.id
}

output "this" {
  value = panos_service_object.this
}
```

[top](#index)