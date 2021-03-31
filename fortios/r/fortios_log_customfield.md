# fortios_log_customfield

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
module "fortios_log_customfield" {
  source = "./modules/fortios/r/fortios_log_customfield"

  # fosid - (optional) is a type of string
  fosid = null
  # name - (required) is a type of string
  name = null
  # value - (required) is a type of string
  value = null
}
```

[top](#index)

### Variables

```terraform
variable "fosid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "value" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "fortios_log_customfield" "this" {
  fosid = var.fosid
  name  = var.name
  value = var.value
}
```

[top](#index)

### Outputs

```terraform
output "fosid" {
  description = "returns a string"
  value       = fortios_log_customfield.this.fosid
}

output "id" {
  description = "returns a string"
  value       = fortios_log_customfield.this.id
}

output "this" {
  value = fortios_log_customfield.this
}
```

[top](#index)