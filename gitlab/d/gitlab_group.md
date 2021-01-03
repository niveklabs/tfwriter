# gitlab_group

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
module "gitlab_group" {
  source = "./modules/gitlab/d/gitlab_group"

  # full_path - (optional) is a type of string
  full_path = null
  # group_id - (optional) is a type of number
  group_id = null
}
```

[top](#index)

### Variables

```terraform
variable "full_path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group_id" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "gitlab_group" "this" {
  full_path = var.full_path
  group_id  = var.group_id
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.gitlab_group.this.description
}

output "full_name" {
  description = "returns a string"
  value       = data.gitlab_group.this.full_name
}

output "full_path" {
  description = "returns a string"
  value       = data.gitlab_group.this.full_path
}

output "group_id" {
  description = "returns a number"
  value       = data.gitlab_group.this.group_id
}

output "id" {
  description = "returns a string"
  value       = data.gitlab_group.this.id
}

output "lfs_enabled" {
  description = "returns a bool"
  value       = data.gitlab_group.this.lfs_enabled
}

output "name" {
  description = "returns a string"
  value       = data.gitlab_group.this.name
}

output "parent_id" {
  description = "returns a number"
  value       = data.gitlab_group.this.parent_id
}

output "path" {
  description = "returns a string"
  value       = data.gitlab_group.this.path
}

output "request_access_enabled" {
  description = "returns a bool"
  value       = data.gitlab_group.this.request_access_enabled
}

output "runners_token" {
  description = "returns a string"
  value       = data.gitlab_group.this.runners_token
  sensitive   = true
}

output "visibility_level" {
  description = "returns a string"
  value       = data.gitlab_group.this.visibility_level
}

output "web_url" {
  description = "returns a string"
  value       = data.gitlab_group.this.web_url
}

output "this" {
  value = gitlab_group.this
}
```

[top](#index)