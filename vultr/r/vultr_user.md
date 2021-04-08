# vultr_user

[back](../vultr.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vultr = ">= 2.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vultr_user" {
  source = "./modules/vultr/r/vultr_user"

  # acl - (optional) is a type of list of string
  acl = []
  # api_enabled - (optional) is a type of bool
  api_enabled = null
  # email - (required) is a type of string
  email = null
  # name - (required) is a type of string
  name = null
  # password - (required) is a type of string
  password = null
}
```

[top](#index)

### Variables

```terraform
variable "acl" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "api_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "email" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "password" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "vultr_user" "this" {
  # acl - (optional) is a type of list of string
  acl = var.acl
  # api_enabled - (optional) is a type of bool
  api_enabled = var.api_enabled
  # email - (required) is a type of string
  email = var.email
  # name - (required) is a type of string
  name = var.name
  # password - (required) is a type of string
  password = var.password
}
```

[top](#index)

### Outputs

```terraform
output "api_key" {
  description = "returns a string"
  value       = vultr_user.this.api_key
}

output "id" {
  description = "returns a string"
  value       = vultr_user.this.id
}

output "this" {
  value = vultr_user.this
}
```

[top](#index)