# gitlab_group

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
    gitlab = ">= 3.3.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "gitlab_group" {
  source = "./modules/gitlab/r/gitlab_group"

  # auto_devops_enabled - (optional) is a type of bool
  auto_devops_enabled = null
  # description - (optional) is a type of string
  description = null
  # emails_disabled - (optional) is a type of bool
  emails_disabled = null
  # lfs_enabled - (optional) is a type of bool
  lfs_enabled = null
  # mentions_disabled - (optional) is a type of bool
  mentions_disabled = null
  # name - (required) is a type of string
  name = null
  # parent_id - (optional) is a type of number
  parent_id = null
  # path - (required) is a type of string
  path = null
  # project_creation_level - (optional) is a type of string
  project_creation_level = null
  # request_access_enabled - (optional) is a type of bool
  request_access_enabled = null
  # require_two_factor_authentication - (optional) is a type of bool
  require_two_factor_authentication = null
  # share_with_group_lock - (optional) is a type of bool
  share_with_group_lock = null
  # subgroup_creation_level - (optional) is a type of string
  subgroup_creation_level = null
  # two_factor_grace_period - (optional) is a type of number
  two_factor_grace_period = null
  # visibility_level - (optional) is a type of string
  visibility_level = null
}
```

[top](#index)

### Variables

```terraform
variable "auto_devops_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "emails_disabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "lfs_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "mentions_disabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "parent_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "path" {
  description = "(required)"
  type        = string
}

variable "project_creation_level" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "request_access_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "require_two_factor_authentication" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "share_with_group_lock" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "subgroup_creation_level" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "two_factor_grace_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "visibility_level" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "gitlab_group" "this" {
  auto_devops_enabled               = var.auto_devops_enabled
  description                       = var.description
  emails_disabled                   = var.emails_disabled
  lfs_enabled                       = var.lfs_enabled
  mentions_disabled                 = var.mentions_disabled
  name                              = var.name
  parent_id                         = var.parent_id
  path                              = var.path
  project_creation_level            = var.project_creation_level
  request_access_enabled            = var.request_access_enabled
  require_two_factor_authentication = var.require_two_factor_authentication
  share_with_group_lock             = var.share_with_group_lock
  subgroup_creation_level           = var.subgroup_creation_level
  two_factor_grace_period           = var.two_factor_grace_period
  visibility_level                  = var.visibility_level
}
```

[top](#index)

### Outputs

```terraform
output "full_name" {
  description = "returns a string"
  value       = gitlab_group.this.full_name
}

output "full_path" {
  description = "returns a string"
  value       = gitlab_group.this.full_path
}

output "id" {
  description = "returns a string"
  value       = gitlab_group.this.id
}

output "runners_token" {
  description = "returns a string"
  value       = gitlab_group.this.runners_token
  sensitive   = true
}

output "visibility_level" {
  description = "returns a string"
  value       = gitlab_group.this.visibility_level
}

output "web_url" {
  description = "returns a string"
  value       = gitlab_group.this.web_url
}

output "this" {
  value = gitlab_group.this
}
```

[top](#index)