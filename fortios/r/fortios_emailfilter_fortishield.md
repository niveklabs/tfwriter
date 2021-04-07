# fortios_emailfilter_fortishield

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
module "fortios_emailfilter_fortishield" {
  source = "./modules/fortios/r/fortios_emailfilter_fortishield"

  # spam_submit_force - (optional) is a type of string
  spam_submit_force = null
  # spam_submit_srv - (optional) is a type of string
  spam_submit_srv = null
  # spam_submit_txt2htm - (optional) is a type of string
  spam_submit_txt2htm = null
}
```

[top](#index)

### Variables

```terraform
variable "spam_submit_force" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "spam_submit_srv" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "spam_submit_txt2htm" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_emailfilter_fortishield" "this" {
  # spam_submit_force - (optional) is a type of string
  spam_submit_force = var.spam_submit_force
  # spam_submit_srv - (optional) is a type of string
  spam_submit_srv = var.spam_submit_srv
  # spam_submit_txt2htm - (optional) is a type of string
  spam_submit_txt2htm = var.spam_submit_txt2htm
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_emailfilter_fortishield.this.id
}

output "spam_submit_force" {
  description = "returns a string"
  value       = fortios_emailfilter_fortishield.this.spam_submit_force
}

output "spam_submit_srv" {
  description = "returns a string"
  value       = fortios_emailfilter_fortishield.this.spam_submit_srv
}

output "spam_submit_txt2htm" {
  description = "returns a string"
  value       = fortios_emailfilter_fortishield.this.spam_submit_txt2htm
}

output "this" {
  value = fortios_emailfilter_fortishield.this
}
```

[top](#index)