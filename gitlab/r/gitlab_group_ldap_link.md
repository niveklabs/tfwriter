# gitlab_group_ldap_link

[back](../gitlab.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "gitlab_group_ldap_link" {
  source = "./modules/gitlab/r/gitlab_group_ldap_link"

  # access_level - (required) is a type of string
  access_level = null
  # cn - (required) is a type of string
  cn = null
  # force - (optional) is a type of bool
  force = null
  # group_id - (required) is a type of string
  group_id = null
  # ldap_provider - (required) is a type of string
  ldap_provider = null
}
```

[top](#index)

### Variables

```terraform
variable "access_level" {
  description = "(required)"
  type        = string
}

variable "cn" {
  description = "(required)"
  type        = string
}

variable "force" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "group_id" {
  description = "(required)"
  type        = string
}

variable "ldap_provider" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "gitlab_group_ldap_link" "this" {
  access_level  = var.access_level
  cn            = var.cn
  force         = var.force
  group_id      = var.group_id
  ldap_provider = var.ldap_provider
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = gitlab_group_ldap_link.this.id
}

output "this" {
  value = gitlab_group_ldap_link.this
}
```

[top](#index)