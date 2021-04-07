# fortios_log_guidisplay

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
module "fortios_log_guidisplay" {
  source = "./modules/fortios/r/fortios_log_guidisplay"

  # fortiview_unscanned_apps - (optional) is a type of string
  fortiview_unscanned_apps = null
  # resolve_apps - (optional) is a type of string
  resolve_apps = null
  # resolve_hosts - (optional) is a type of string
  resolve_hosts = null
}
```

[top](#index)

### Variables

```terraform
variable "fortiview_unscanned_apps" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resolve_apps" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resolve_hosts" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_log_guidisplay" "this" {
  # fortiview_unscanned_apps - (optional) is a type of string
  fortiview_unscanned_apps = var.fortiview_unscanned_apps
  # resolve_apps - (optional) is a type of string
  resolve_apps = var.resolve_apps
  # resolve_hosts - (optional) is a type of string
  resolve_hosts = var.resolve_hosts
}
```

[top](#index)

### Outputs

```terraform
output "fortiview_unscanned_apps" {
  description = "returns a string"
  value       = fortios_log_guidisplay.this.fortiview_unscanned_apps
}

output "id" {
  description = "returns a string"
  value       = fortios_log_guidisplay.this.id
}

output "resolve_apps" {
  description = "returns a string"
  value       = fortios_log_guidisplay.this.resolve_apps
}

output "resolve_hosts" {
  description = "returns a string"
  value       = fortios_log_guidisplay.this.resolve_hosts
}

output "this" {
  value = fortios_log_guidisplay.this
}
```

[top](#index)