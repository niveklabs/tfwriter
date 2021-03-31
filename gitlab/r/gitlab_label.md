# gitlab_label

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
module "gitlab_label" {
  source = "./modules/gitlab/r/gitlab_label"

  # color - (required) is a type of string
  color = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # project - (required) is a type of string
  project = null
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

variable "name" {
  description = "(required)"
  type        = string
}

variable "project" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "gitlab_label" "this" {
  color       = var.color
  description = var.description
  name        = var.name
  project     = var.project
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = gitlab_label.this.id
}

output "this" {
  value = gitlab_label.this
}
```

[top](#index)