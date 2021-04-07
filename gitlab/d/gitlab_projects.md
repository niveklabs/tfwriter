# gitlab_projects

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
module "gitlab_projects" {
  source = "./modules/gitlab/d/gitlab_projects"

  # archived - (optional) is a type of bool
  archived = null
  # group_id - (optional) is a type of number
  group_id = null
  # include_subgroups - (optional) is a type of bool
  include_subgroups = null
  # max_queryable_pages - (optional) is a type of number
  max_queryable_pages = null
  # membership - (optional) is a type of bool
  membership = null
  # min_access_level - (optional) is a type of number
  min_access_level = null
  # order_by - (optional) is a type of string
  order_by = null
  # owned - (optional) is a type of bool
  owned = null
  # page - (optional) is a type of number
  page = null
  # per_page - (optional) is a type of number
  per_page = null
  # search - (optional) is a type of string
  search = null
  # simple - (optional) is a type of bool
  simple = null
  # sort - (optional) is a type of string
  sort = null
  # starred - (optional) is a type of bool
  starred = null
  # statistics - (optional) is a type of bool
  statistics = null
  # visibility - (optional) is a type of string
  visibility = null
  # with_custom_attributes - (optional) is a type of bool
  with_custom_attributes = null
  # with_issues_enabled - (optional) is a type of bool
  with_issues_enabled = null
  # with_merge_requests_enabled - (optional) is a type of bool
  with_merge_requests_enabled = null
  # with_programming_language - (optional) is a type of string
  with_programming_language = null
  # with_shared - (optional) is a type of bool
  with_shared = null
}
```

[top](#index)

### Variables

```terraform
variable "archived" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "group_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "include_subgroups" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "max_queryable_pages" {
  description = "(optional) - Prevents overloading your Gitlab instance in case of a misconfiguration."
  type        = number
  default     = null
}

variable "membership" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "min_access_level" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "order_by" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "owned" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "page" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "per_page" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "search" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "simple" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "sort" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "starred" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "statistics" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "visibility" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "with_custom_attributes" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "with_issues_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "with_merge_requests_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "with_programming_language" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "with_shared" {
  description = "(optional)"
  type        = bool
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "gitlab_projects" "this" {
  archived                    = var.archived
  group_id                    = var.group_id
  include_subgroups           = var.include_subgroups
  max_queryable_pages         = var.max_queryable_pages
  membership                  = var.membership
  min_access_level            = var.min_access_level
  order_by                    = var.order_by
  owned                       = var.owned
  page                        = var.page
  per_page                    = var.per_page
  search                      = var.search
  simple                      = var.simple
  sort                        = var.sort
  starred                     = var.starred
  statistics                  = var.statistics
  visibility                  = var.visibility
  with_custom_attributes      = var.with_custom_attributes
  with_issues_enabled         = var.with_issues_enabled
  with_merge_requests_enabled = var.with_merge_requests_enabled
  with_programming_language   = var.with_programming_language
  with_shared                 = var.with_shared
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.gitlab_projects.this.id
}

output "projects" {
  description = "returns a list of object"
  value       = data.gitlab_projects.this.projects
}

output "this" {
  value = gitlab_projects.this
}
```

[top](#index)