# fortios_switchcontroller_remotelog

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
module "fortios_switchcontroller_remotelog" {
  source = "./modules/fortios/r/fortios_switchcontroller_remotelog"

  # csv - (optional) is a type of string
  csv = null
  # facility - (optional) is a type of string
  facility = null
  # name - (optional) is a type of string
  name = null
  # port - (optional) is a type of number
  port = null
  # server - (optional) is a type of string
  server = null
  # severity - (optional) is a type of string
  severity = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "csv" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "facility" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "severity" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_switchcontroller_remotelog" "this" {
  csv      = var.csv
  facility = var.facility
  name     = var.name
  port     = var.port
  server   = var.server
  severity = var.severity
  status   = var.status
}
```

[top](#index)

### Outputs

```terraform
output "csv" {
  description = "returns a string"
  value       = fortios_switchcontroller_remotelog.this.csv
}

output "facility" {
  description = "returns a string"
  value       = fortios_switchcontroller_remotelog.this.facility
}

output "id" {
  description = "returns a string"
  value       = fortios_switchcontroller_remotelog.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_switchcontroller_remotelog.this.name
}

output "port" {
  description = "returns a number"
  value       = fortios_switchcontroller_remotelog.this.port
}

output "server" {
  description = "returns a string"
  value       = fortios_switchcontroller_remotelog.this.server
}

output "severity" {
  description = "returns a string"
  value       = fortios_switchcontroller_remotelog.this.severity
}

output "status" {
  description = "returns a string"
  value       = fortios_switchcontroller_remotelog.this.status
}

output "this" {
  value = fortios_switchcontroller_remotelog.this
}
```

[top](#index)