# google_projects

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    google = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "google_projects" {
  source = "./modules/google/d/google_projects"

  # filter - (required) is a type of string
  filter = null
}
```

[top](#index)

### Variables

```hcl
variable "filter" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```hcl
data "google_projects" "this" {
  filter = var.filter
}
```

[top](#index)

### Outputs

```hcl
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