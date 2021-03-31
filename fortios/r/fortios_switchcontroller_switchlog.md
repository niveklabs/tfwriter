# fortios_switchcontroller_switchlog

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
module "fortios_switchcontroller_switchlog" {
  source = "./modules/fortios/r/fortios_switchcontroller_switchlog"

  # severity - (optional) is a type of string
  severity = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
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
resource "fortios_switchcontroller_switchlog" "this" {
  severity = var.severity
  status   = var.status
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_switchcontroller_switchlog.this.id
}

output "severity" {
  description = "returns a string"
  value       = fortios_switchcontroller_switchlog.this.severity
}

output "status" {
  description = "returns a string"
  value       = fortios_switchcontroller_switchlog.this.status
}

output "this" {
  value = fortios_switchcontroller_switchlog.this
}
```

[top](#index)