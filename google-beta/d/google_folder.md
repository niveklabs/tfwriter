# google_folder

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
module "google_folder" {
  source = "./modules/google-beta/d/google_folder"

  # folder - (required) is a type of string
  folder = null
  # lookup_organization - (optional) is a type of bool
  lookup_organization = null
}
```

[top](#index)

### Variables

```terraform
variable "folder" {
  description = "(required)"
  type        = string
}

variable "lookup_organization" {
  description = "(optional)"
  type        = bool
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "google_folder" "this" {
  folder              = var.folder
  lookup_organization = var.lookup_organization
}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = data.google_folder.this.create_time
}

output "display_name" {
  description = "returns a string"
  value       = data.google_folder.this.display_name
}

output "folder_id" {
  description = "returns a string"
  value       = data.google_folder.this.folder_id
}

output "id" {
  description = "returns a string"
  value       = data.google_folder.this.id
}

output "lifecycle_state" {
  description = "returns a string"
  value       = data.google_folder.this.lifecycle_state
}

output "name" {
  description = "returns a string"
  value       = data.google_folder.this.name
}

output "organization" {
  description = "returns a string"
  value       = data.google_folder.this.organization
}

output "parent" {
  description = "returns a string"
  value       = data.google_folder.this.parent
}

output "this" {
  value = google_folder.this
}
```

[top](#index)