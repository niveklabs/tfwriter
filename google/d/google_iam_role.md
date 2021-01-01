# google_iam_role

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
module "google_iam_role" {
  source = "./modules/google/d/google_iam_role"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```hcl
variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```hcl
data "google_iam_role" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = data.google_iam_role.this.id
}

output "included_permissions" {
  description = "returns a list of string"
  value       = data.google_iam_role.this.included_permissions
}

output "stage" {
  description = "returns a string"
  value       = data.google_iam_role.this.stage
}

output "title" {
  description = "returns a string"
  value       = data.google_iam_role.this.title
}

output "this" {
  value = google_iam_role.this
}
```

[top](#index)