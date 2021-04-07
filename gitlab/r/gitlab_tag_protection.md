# gitlab_tag_protection

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
module "gitlab_tag_protection" {
  source = "./modules/gitlab/r/gitlab_tag_protection"

  # create_access_level - (required) is a type of string
  create_access_level = null
  # project - (required) is a type of string
  project = null
  # tag - (required) is a type of string
  tag = null
}
```

[top](#index)

### Variables

```terraform
variable "create_access_level" {
  description = "(required)"
  type        = string
}

variable "project" {
  description = "(required)"
  type        = string
}

variable "tag" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "gitlab_tag_protection" "this" {
  # create_access_level - (required) is a type of string
  create_access_level = var.create_access_level
  # project - (required) is a type of string
  project = var.project
  # tag - (required) is a type of string
  tag = var.tag
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = gitlab_tag_protection.this.id
}

output "this" {
  value = gitlab_tag_protection.this
}
```

[top](#index)