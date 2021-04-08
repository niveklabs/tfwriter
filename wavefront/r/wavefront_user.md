# wavefront_user

[back](../wavefront.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    wavefront = ">= 2.8.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "wavefront_user" {
  source = "./modules/wavefront/r/wavefront_user"

  # customer - (optional) is a type of string
  customer = null
  # email - (required) is a type of string
  email = null
  # permissions - (optional) is a type of set of string
  permissions = []
  # user_groups - (optional) is a type of set of string
  user_groups = []
}
```

[top](#index)

### Variables

```terraform
variable "customer" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "email" {
  description = "(required)"
  type        = string
}

variable "permissions" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "user_groups" {
  description = "(optional)"
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "wavefront_user" "this" {
  # customer - (optional) is a type of string
  customer = var.customer
  # email - (required) is a type of string
  email = var.email
  # permissions - (optional) is a type of set of string
  permissions = var.permissions
  # user_groups - (optional) is a type of set of string
  user_groups = var.user_groups
}
```

[top](#index)

### Outputs

```terraform
output "customer" {
  description = "returns a string"
  value       = wavefront_user.this.customer
}

output "id" {
  description = "returns a string"
  value       = wavefront_user.this.id
}

output "permissions" {
  description = "returns a set of string"
  value       = wavefront_user.this.permissions
}

output "user_groups" {
  description = "returns a set of string"
  value       = wavefront_user.this.user_groups
}

output "this" {
  value = wavefront_user.this
}
```

[top](#index)