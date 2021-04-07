# avi_useraccount

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    avi = ">= 0.2.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "avi_useraccount" {
  source = "./modules/avi/r/avi_useraccount"

  # email - (optional) is a type of string
  email = null
  # full_name - (optional) is a type of string
  full_name = null
  # local - (optional) is a type of bool
  local = null
  # name - (optional) is a type of string
  name = null
  # old_password - (optional) is a type of string
  old_password = null
  # password - (optional) is a type of string
  password = null
  # username - (optional) is a type of string
  username = null
}
```

[top](#index)

### Variables

```terraform
variable "email" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "full_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "local" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "old_password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "username" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "avi_useraccount" "this" {
  # email - (optional) is a type of string
  email = var.email
  # full_name - (optional) is a type of string
  full_name = var.full_name
  # local - (optional) is a type of bool
  local = var.local
  # name - (optional) is a type of string
  name = var.name
  # old_password - (optional) is a type of string
  old_password = var.old_password
  # password - (optional) is a type of string
  password = var.password
  # username - (optional) is a type of string
  username = var.username
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = avi_useraccount.this.id
}

output "this" {
  value = avi_useraccount.this
}
```

[top](#index)