# checkpoint_management_set_login_message

[back](../checkpoint.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    checkpoint = ">= 1.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "checkpoint_management_set_login_message" {
  source = "./modules/checkpoint/r/checkpoint_management_set_login_message"

  # header - (optional) is a type of string
  header = null
  # message - (optional) is a type of string
  message = null
  # show_message - (optional) is a type of bool
  show_message = null
  # warning - (optional) is a type of bool
  warning = null
}
```

[top](#index)

### Variables

```terraform
variable "header" {
  description = "(optional) - Login message header."
  type        = string
  default     = null
}

variable "message" {
  description = "(optional) - Login message body."
  type        = string
  default     = null
}

variable "show_message" {
  description = "(optional) - Whether to show login message."
  type        = bool
  default     = null
}

variable "warning" {
  description = "(optional) - Add warning sign."
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_set_login_message" "this" {
  header       = var.header
  message      = var.message
  show_message = var.show_message
  warning      = var.warning
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_set_login_message.this.id
}

output "this" {
  value = checkpoint_management_set_login_message.this
}
```

[top](#index)