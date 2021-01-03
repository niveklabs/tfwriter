# gitlab_group_label

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
module "gitlab_group_label" {
  source = "./modules/gitlab/r/gitlab_group_label"

  # color - (required) is a type of string
  color = null
  # description - (optional) is a type of string
  description = null
  # group - (required) is a type of string
  group = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "color" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "gitlab_group_label" "this" {
  color       = var.color
  description = var.description
  group       = var.group
  name        = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = gitlab_group_label.this.id
}

output "this" {
  value = gitlab_group_label.this
}
```

[top](#index)