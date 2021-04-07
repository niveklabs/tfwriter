# alicloud_ram_user

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_ram_user" {
  source = "./modules/alicloud/r/alicloud_ram_user"

  # comments - (optional) is a type of string
  comments = null
  # display_name - (optional) is a type of string
  display_name = null
  # email - (optional) is a type of string
  email = null
  # force - (optional) is a type of bool
  force = null
  # mobile - (optional) is a type of string
  mobile = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "comments" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "email" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "force" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "mobile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_ram_user" "this" {
  # comments - (optional) is a type of string
  comments = var.comments
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # email - (optional) is a type of string
  email = var.email
  # force - (optional) is a type of bool
  force = var.force
  # mobile - (optional) is a type of string
  mobile = var.mobile
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_ram_user.this.id
}

output "this" {
  value = alicloud_ram_user.this
}
```

[top](#index)