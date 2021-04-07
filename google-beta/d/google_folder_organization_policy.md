# google_folder_organization_policy

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
module "google_folder_organization_policy" {
  source = "./modules/google-beta/d/google_folder_organization_policy"

  # constraint - (required) is a type of string
  constraint = null
  # folder - (required) is a type of string
  folder = null
}
```

[top](#index)

### Variables

```terraform
variable "constraint" {
  description = "(required) - The name of the Constraint the Policy is configuring, for example, serviceuser.services."
  type        = string
}

variable "folder" {
  description = "(required) - The resource name of the folder to set the policy for. Its format is folders/{folder_id}."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "google_folder_organization_policy" "this" {
  # constraint - (required) is a type of string
  constraint = var.constraint
  # folder - (required) is a type of string
  folder = var.folder
}
```

[top](#index)

### Outputs

```terraform
output "boolean_policy" {
  description = "returns a list of object"
  value       = data.google_folder_organization_policy.this.boolean_policy
}

output "etag" {
  description = "returns a string"
  value       = data.google_folder_organization_policy.this.etag
}

output "id" {
  description = "returns a string"
  value       = data.google_folder_organization_policy.this.id
}

output "list_policy" {
  description = "returns a list of object"
  value       = data.google_folder_organization_policy.this.list_policy
}

output "restore_policy" {
  description = "returns a list of object"
  value       = data.google_folder_organization_policy.this.restore_policy
}

output "update_time" {
  description = "returns a string"
  value       = data.google_folder_organization_policy.this.update_time
}

output "version" {
  description = "returns a number"
  value       = data.google_folder_organization_policy.this.version
}

output "this" {
  value = google_folder_organization_policy.this
}
```

[top](#index)