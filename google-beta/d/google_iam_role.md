# google_iam_role

[back](../google-beta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "google_iam_role" {
  source = "./modules/google-beta/d/google_iam_role"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "google_iam_role" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
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