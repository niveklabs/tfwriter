# google_projects

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google = ">= 3.62.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_projects" {
  source = "./modules/google/d/google_projects"

  # filter - (required) is a type of string
  filter = null
}
```

[top](#index)

### Variables

```terraform
variable "filter" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "google_projects" "this" {
  filter = var.filter
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.google_projects.this.id
}

output "projects" {
  description = "returns a list of object"
  value       = data.google_projects.this.projects
}

output "this" {
  value = google_projects.this
}
```

[top](#index)