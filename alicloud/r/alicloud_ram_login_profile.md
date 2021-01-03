# alicloud_ram_login_profile

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
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_ram_login_profile" {
  source = "./modules/alicloud/r/alicloud_ram_login_profile"

  # mfa_bind_required - (optional) is a type of bool
  mfa_bind_required = null
  # password - (required) is a type of string
  password = null
  # password_reset_required - (optional) is a type of bool
  password_reset_required = null
  # user_name - (required) is a type of string
  user_name = null
}
```

[top](#index)

### Variables

```terraform
variable "mfa_bind_required" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "password" {
  description = "(required)"
  type        = string
}

variable "password_reset_required" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "user_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_ram_login_profile" "this" {
  mfa_bind_required       = var.mfa_bind_required
  password                = var.password
  password_reset_required = var.password_reset_required
  user_name               = var.user_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_ram_login_profile.this.id
}

output "this" {
  value = alicloud_ram_login_profile.this
}
```

[top](#index)