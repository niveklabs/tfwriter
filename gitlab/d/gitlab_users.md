# gitlab_users

[back](../gitlab.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    gitlab = ">= 3.6.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "gitlab_users" {
  source = "./modules/gitlab/d/gitlab_users"

  # active - (optional) is a type of bool
  active = null
  # blocked - (optional) is a type of bool
  blocked = null
  # created_after - (optional) is a type of string
  created_after = null
  # created_before - (optional) is a type of string
  created_before = null
  # extern_provider - (optional) is a type of string
  extern_provider = null
  # extern_uid - (optional) is a type of string
  extern_uid = null
  # order_by - (optional) is a type of string
  order_by = null
  # search - (optional) is a type of string
  search = null
  # sort - (optional) is a type of string
  sort = null
}
```

[top](#index)

### Variables

```terraform
variable "active" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "blocked" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "created_after" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "created_before" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "extern_provider" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "extern_uid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "order_by" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "search" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sort" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "gitlab_users" "this" {
  # active - (optional) is a type of bool
  active = var.active
  # blocked - (optional) is a type of bool
  blocked = var.blocked
  # created_after - (optional) is a type of string
  created_after = var.created_after
  # created_before - (optional) is a type of string
  created_before = var.created_before
  # extern_provider - (optional) is a type of string
  extern_provider = var.extern_provider
  # extern_uid - (optional) is a type of string
  extern_uid = var.extern_uid
  # order_by - (optional) is a type of string
  order_by = var.order_by
  # search - (optional) is a type of string
  search = var.search
  # sort - (optional) is a type of string
  sort = var.sort
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.gitlab_users.this.id
}

output "users" {
  description = "returns a list of object"
  value       = data.gitlab_users.this.users
}

output "this" {
  value = gitlab_users.this
}
```

[top](#index)