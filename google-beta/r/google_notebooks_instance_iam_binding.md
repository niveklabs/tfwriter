# google_notebooks_instance_iam_binding

[back](../google-beta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google-beta = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_notebooks_instance_iam_binding" {
  source = "./modules/google-beta/r/google_notebooks_instance_iam_binding"

  # instance_name - (required) is a type of string
  instance_name = null
  # location - (optional) is a type of string
  location = null
  # members - (required) is a type of set of string
  members = []
  # project - (optional) is a type of string
  project = null
  # role - (required) is a type of string
  role = null

  condition = [{
    description = null
    expression  = null
    title       = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "instance_name" {
  description = "(required)"
  type        = string
}

variable "location" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "members" {
  description = "(required)"
  type        = set(string)
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "role" {
  description = "(required)"
  type        = string
}

variable "condition" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      description = string
      expression  = string
      title       = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_notebooks_instance_iam_binding" "this" {
  # instance_name - (required) is a type of string
  instance_name = var.instance_name
  # location - (optional) is a type of string
  location = var.location
  # members - (required) is a type of set of string
  members = var.members
  # project - (optional) is a type of string
  project = var.project
  # role - (required) is a type of string
  role = var.role

  dynamic "condition" {
    for_each = var.condition
    content {
      # description - (optional) is a type of string
      description = condition.value["description"]
      # expression - (required) is a type of string
      expression = condition.value["expression"]
      # title - (required) is a type of string
      title = condition.value["title"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "etag" {
  description = "returns a string"
  value       = google_notebooks_instance_iam_binding.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_notebooks_instance_iam_binding.this.id
}

output "location" {
  description = "returns a string"
  value       = google_notebooks_instance_iam_binding.this.location
}

output "project" {
  description = "returns a string"
  value       = google_notebooks_instance_iam_binding.this.project
}

output "this" {
  value = google_notebooks_instance_iam_binding.this
}
```

[top](#index)