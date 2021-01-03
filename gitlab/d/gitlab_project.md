# gitlab_project

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
    gitlab = ">= 3.3.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "gitlab_project" {
  source = "./modules/gitlab/d/gitlab_project"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "gitlab_project" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "archived" {
  description = "returns a bool"
  value       = data.gitlab_project.this.archived
}

output "default_branch" {
  description = "returns a string"
  value       = data.gitlab_project.this.default_branch
}

output "description" {
  description = "returns a string"
  value       = data.gitlab_project.this.description
}

output "http_url_to_repo" {
  description = "returns a string"
  value       = data.gitlab_project.this.http_url_to_repo
}

output "id" {
  description = "returns a number"
  value       = data.gitlab_project.this.id
}

output "issues_enabled" {
  description = "returns a bool"
  value       = data.gitlab_project.this.issues_enabled
}

output "lfs_enabled" {
  description = "returns a bool"
  value       = data.gitlab_project.this.lfs_enabled
}

output "merge_requests_enabled" {
  description = "returns a bool"
  value       = data.gitlab_project.this.merge_requests_enabled
}

output "name" {
  description = "returns a string"
  value       = data.gitlab_project.this.name
}

output "namespace_id" {
  description = "returns a number"
  value       = data.gitlab_project.this.namespace_id
}

output "path" {
  description = "returns a string"
  value       = data.gitlab_project.this.path
}

output "path_with_namespace" {
  description = "returns a string"
  value       = data.gitlab_project.this.path_with_namespace
}

output "pipelines_enabled" {
  description = "returns a bool"
  value       = data.gitlab_project.this.pipelines_enabled
}

output "push_rules" {
  description = "returns a list of object"
  value       = data.gitlab_project.this.push_rules
}

output "remove_source_branch_after_merge" {
  description = "returns a bool"
  value       = data.gitlab_project.this.remove_source_branch_after_merge
}

output "request_access_enabled" {
  description = "returns a bool"
  value       = data.gitlab_project.this.request_access_enabled
}

output "runners_token" {
  description = "returns a string"
  value       = data.gitlab_project.this.runners_token
}

output "snippets_enabled" {
  description = "returns a bool"
  value       = data.gitlab_project.this.snippets_enabled
}

output "ssh_url_to_repo" {
  description = "returns a string"
  value       = data.gitlab_project.this.ssh_url_to_repo
}

output "visibility_level" {
  description = "returns a string"
  value       = data.gitlab_project.this.visibility_level
}

output "web_url" {
  description = "returns a string"
  value       = data.gitlab_project.this.web_url
}

output "wiki_enabled" {
  description = "returns a bool"
  value       = data.gitlab_project.this.wiki_enabled
}

output "this" {
  value = gitlab_project.this
}
```

[top](#index)