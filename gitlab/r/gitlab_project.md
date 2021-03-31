# gitlab_project

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
    gitlab = ">= 3.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "gitlab_project" {
  source = "./modules/gitlab/r/gitlab_project"

  # approvals_before_merge - (optional) is a type of number
  approvals_before_merge = null
  # archived - (optional) is a type of bool
  archived = null
  # container_registry_enabled - (optional) is a type of bool
  container_registry_enabled = null
  # default_branch - (optional) is a type of string
  default_branch = null
  # description - (optional) is a type of string
  description = null
  # group_with_project_templates_id - (optional) is a type of number
  group_with_project_templates_id = null
  # import_url - (optional) is a type of string
  import_url = null
  # initialize_with_readme - (optional) is a type of bool
  initialize_with_readme = null
  # issues_enabled - (optional) is a type of bool
  issues_enabled = null
  # lfs_enabled - (optional) is a type of bool
  lfs_enabled = null
  # merge_method - (optional) is a type of string
  merge_method = null
  # merge_requests_enabled - (optional) is a type of bool
  merge_requests_enabled = null
  # mirror - (optional) is a type of bool
  mirror = null
  # mirror_overwrites_diverged_branches - (optional) is a type of bool
  mirror_overwrites_diverged_branches = null
  # mirror_trigger_builds - (optional) is a type of bool
  mirror_trigger_builds = null
  # name - (required) is a type of string
  name = null
  # namespace_id - (optional) is a type of number
  namespace_id = null
  # only_allow_merge_if_all_discussions_are_resolved - (optional) is a type of bool
  only_allow_merge_if_all_discussions_are_resolved = null
  # only_allow_merge_if_pipeline_succeeds - (optional) is a type of bool
  only_allow_merge_if_pipeline_succeeds = null
  # only_mirror_protected_branches - (optional) is a type of bool
  only_mirror_protected_branches = null
  # packages_enabled - (optional) is a type of bool
  packages_enabled = null
  # pages_access_level - (optional) is a type of string
  pages_access_level = null
  # path - (optional) is a type of string
  path = null
  # pipelines_enabled - (optional) is a type of bool
  pipelines_enabled = null
  # remove_source_branch_after_merge - (optional) is a type of bool
  remove_source_branch_after_merge = null
  # request_access_enabled - (optional) is a type of bool
  request_access_enabled = null
  # shared_runners_enabled - (optional) is a type of bool
  shared_runners_enabled = null
  # snippets_enabled - (optional) is a type of bool
  snippets_enabled = null
  # tags - (optional) is a type of set of string
  tags = []
  # template_name - (optional) is a type of string
  template_name = null
  # template_project_id - (optional) is a type of number
  template_project_id = null
  # use_custom_template - (optional) is a type of bool
  use_custom_template = null
  # visibility_level - (optional) is a type of string
  visibility_level = null
  # wiki_enabled - (optional) is a type of bool
  wiki_enabled = null

  push_rules = [{
    author_email_regex            = null
    branch_name_regex             = null
    commit_committer_check        = null
    commit_message_negative_regex = null
    commit_message_regex          = null
    deny_delete_tag               = null
    file_name_regex               = null
    max_file_size                 = null
    member_check                  = null
    prevent_secrets               = null
    reject_unsigned_commits       = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "approvals_before_merge" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "archived" {
  description = "(optional) - Whether the project is archived."
  type        = bool
  default     = null
}

variable "container_registry_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "default_branch" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group_with_project_templates_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "import_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "initialize_with_readme" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "issues_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "lfs_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "merge_method" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "merge_requests_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "mirror" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "mirror_overwrites_diverged_branches" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "mirror_trigger_builds" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "namespace_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "only_allow_merge_if_all_discussions_are_resolved" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "only_allow_merge_if_pipeline_succeeds" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "only_mirror_protected_branches" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "packages_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "pages_access_level" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pipelines_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "remove_source_branch_after_merge" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "request_access_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "shared_runners_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "snippets_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "template_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_project_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "use_custom_template" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "visibility_level" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wiki_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "push_rules" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      author_email_regex            = string
      branch_name_regex             = string
      commit_committer_check        = bool
      commit_message_negative_regex = string
      commit_message_regex          = string
      deny_delete_tag               = bool
      file_name_regex               = string
      max_file_size                 = number
      member_check                  = bool
      prevent_secrets               = bool
      reject_unsigned_commits       = bool
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "gitlab_project" "this" {
  approvals_before_merge                           = var.approvals_before_merge
  archived                                         = var.archived
  container_registry_enabled                       = var.container_registry_enabled
  default_branch                                   = var.default_branch
  description                                      = var.description
  group_with_project_templates_id                  = var.group_with_project_templates_id
  import_url                                       = var.import_url
  initialize_with_readme                           = var.initialize_with_readme
  issues_enabled                                   = var.issues_enabled
  lfs_enabled                                      = var.lfs_enabled
  merge_method                                     = var.merge_method
  merge_requests_enabled                           = var.merge_requests_enabled
  mirror                                           = var.mirror
  mirror_overwrites_diverged_branches              = var.mirror_overwrites_diverged_branches
  mirror_trigger_builds                            = var.mirror_trigger_builds
  name                                             = var.name
  namespace_id                                     = var.namespace_id
  only_allow_merge_if_all_discussions_are_resolved = var.only_allow_merge_if_all_discussions_are_resolved
  only_allow_merge_if_pipeline_succeeds            = var.only_allow_merge_if_pipeline_succeeds
  only_mirror_protected_branches                   = var.only_mirror_protected_branches
  packages_enabled                                 = var.packages_enabled
  pages_access_level                               = var.pages_access_level
  path                                             = var.path
  pipelines_enabled                                = var.pipelines_enabled
  remove_source_branch_after_merge                 = var.remove_source_branch_after_merge
  request_access_enabled                           = var.request_access_enabled
  shared_runners_enabled                           = var.shared_runners_enabled
  snippets_enabled                                 = var.snippets_enabled
  tags                                             = var.tags
  template_name                                    = var.template_name
  template_project_id                              = var.template_project_id
  use_custom_template                              = var.use_custom_template
  visibility_level                                 = var.visibility_level
  wiki_enabled                                     = var.wiki_enabled

  dynamic "push_rules" {
    for_each = var.push_rules
    content {
      author_email_regex            = push_rules.value["author_email_regex"]
      branch_name_regex             = push_rules.value["branch_name_regex"]
      commit_committer_check        = push_rules.value["commit_committer_check"]
      commit_message_negative_regex = push_rules.value["commit_message_negative_regex"]
      commit_message_regex          = push_rules.value["commit_message_regex"]
      deny_delete_tag               = push_rules.value["deny_delete_tag"]
      file_name_regex               = push_rules.value["file_name_regex"]
      max_file_size                 = push_rules.value["max_file_size"]
      member_check                  = push_rules.value["member_check"]
      prevent_secrets               = push_rules.value["prevent_secrets"]
      reject_unsigned_commits       = push_rules.value["reject_unsigned_commits"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "http_url_to_repo" {
  description = "returns a string"
  value       = gitlab_project.this.http_url_to_repo
}

output "id" {
  description = "returns a string"
  value       = gitlab_project.this.id
}

output "namespace_id" {
  description = "returns a number"
  value       = gitlab_project.this.namespace_id
}

output "path_with_namespace" {
  description = "returns a string"
  value       = gitlab_project.this.path_with_namespace
}

output "runners_token" {
  description = "returns a string"
  value       = gitlab_project.this.runners_token
  sensitive   = true
}

output "shared_runners_enabled" {
  description = "returns a bool"
  value       = gitlab_project.this.shared_runners_enabled
}

output "ssh_url_to_repo" {
  description = "returns a string"
  value       = gitlab_project.this.ssh_url_to_repo
}

output "web_url" {
  description = "returns a string"
  value       = gitlab_project.this.web_url
}

output "this" {
  value = gitlab_project.this
}
```

[top](#index)