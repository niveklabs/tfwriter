# gitlab_project_mirror

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
module "gitlab_project_mirror" {
  source = "./modules/gitlab/r/gitlab_project_mirror"

  # enabled - (optional) is a type of bool
  enabled = null
  # keep_divergent_refs - (optional) is a type of bool
  keep_divergent_refs = null
  # only_protected_branches - (optional) is a type of bool
  only_protected_branches = null
  # project - (required) is a type of string
  project = null
  # url - (required) is a type of string
  url = null
}
```

[top](#index)

### Variables

```terraform
variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "keep_divergent_refs" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "only_protected_branches" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "project" {
  description = "(required)"
  type        = string
}

variable "url" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "gitlab_project_mirror" "this" {
  enabled                 = var.enabled
  keep_divergent_refs     = var.keep_divergent_refs
  only_protected_branches = var.only_protected_branches
  project                 = var.project
  url                     = var.url
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = gitlab_project_mirror.this.id
}

output "mirror_id" {
  description = "returns a number"
  value       = gitlab_project_mirror.this.mirror_id
}

output "this" {
  value = gitlab_project_mirror.this
}
```

[top](#index)