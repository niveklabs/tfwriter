# fortios_switchcontroller_snmpsysinfo

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
module "fortios_switchcontroller_snmpsysinfo" {
  source = "./modules/fortios/r/fortios_switchcontroller_snmpsysinfo"

  # contact_info - (optional) is a type of string
  contact_info = null
  # description - (optional) is a type of string
  description = null
  # engine_id - (optional) is a type of string
  engine_id = null
  # location - (optional) is a type of string
  location = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "contact_info" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "engine_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "location" {
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
resource "fortios_switchcontroller_snmpsysinfo" "this" {
  # contact_info - (optional) is a type of string
  contact_info = var.contact_info
  # description - (optional) is a type of string
  description = var.description
  # engine_id - (optional) is a type of string
  engine_id = var.engine_id
  # location - (optional) is a type of string
  location = var.location
  # status - (optional) is a type of string
  status = var.status
}
```

[top](#index)

### Outputs

```terraform
output "contact_info" {
  description = "returns a string"
  value       = fortios_switchcontroller_snmpsysinfo.this.contact_info
}

output "description" {
  description = "returns a string"
  value       = fortios_switchcontroller_snmpsysinfo.this.description
}

output "engine_id" {
  description = "returns a string"
  value       = fortios_switchcontroller_snmpsysinfo.this.engine_id
}

output "id" {
  description = "returns a string"
  value       = fortios_switchcontroller_snmpsysinfo.this.id
}

output "location" {
  description = "returns a string"
  value       = fortios_switchcontroller_snmpsysinfo.this.location
}

output "status" {
  description = "returns a string"
  value       = fortios_switchcontroller_snmpsysinfo.this.status
}

output "this" {
  value = fortios_switchcontroller_snmpsysinfo.this
}
```

[top](#index)