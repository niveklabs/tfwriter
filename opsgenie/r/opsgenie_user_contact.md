# opsgenie_user_contact

[back](../opsgenie.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    opsgenie = ">= 0.6.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "opsgenie_user_contact" {
  source = "./modules/opsgenie/r/opsgenie_user_contact"

  # enabled - (optional) is a type of bool
  enabled = null
  # method - (required) is a type of string
  method = null
  # to - (required) is a type of string
  to = null
  # username - (required) is a type of string
  username = null
}
```

[top](#index)

### Variables

```terraform
variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "method" {
  description = "(required)"
  type        = string
}

variable "to" {
  description = "(required)"
  type        = string
}

variable "username" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "opsgenie_user_contact" "this" {
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # method - (required) is a type of string
  method = var.method
  # to - (required) is a type of string
  to = var.to
  # username - (required) is a type of string
  username = var.username
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = opsgenie_user_contact.this.id
}

output "this" {
  value = opsgenie_user_contact.this
}
```

[top](#index)