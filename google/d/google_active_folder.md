# google_active_folder

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
module "google_active_folder" {
  source = "./modules/google/d/google_active_folder"

  # display_name - (required) is a type of string
  display_name = null
  # parent - (required) is a type of string
  parent = null
}
```

[top](#index)

### Variables

```hcl
variable "display_name" {
  description = "(required)"
  type        = string
}

variable "parent" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```hcl
data "google_active_folder" "this" {
  display_name = var.display_name
  parent       = var.parent
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = data.google_active_folder.this.id
}

output "name" {
  description = "returns a string"
  value       = data.google_active_folder.this.name
}

output "this" {
  value = google_active_folder.this
}
```

[top](#index)