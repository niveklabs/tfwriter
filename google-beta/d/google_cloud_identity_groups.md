# google_cloud_identity_groups

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
    google-beta = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_cloud_identity_groups" {
  source = "./modules/google-beta/d/google_cloud_identity_groups"

  # parent - (required) is a type of string
  parent = null
}
```

[top](#index)

### Variables

```terraform
variable "parent" {
  description = "(required) - The resource name of the entity under which this Group resides in the\nCloud Identity resource hierarchy.\n\nMust be of the form identitysources/{identity_source_id} for external-identity-mapped\ngroups or customers/{customer_id} for Google Groups."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "google_cloud_identity_groups" "this" {
  parent = var.parent
}
```

[top](#index)

### Outputs

```terraform
output "groups" {
  description = "returns a list of object"
  value       = data.google_cloud_identity_groups.this.groups
}

output "id" {
  description = "returns a string"
  value       = data.google_cloud_identity_groups.this.id
}

output "this" {
  value = google_cloud_identity_groups.this
}
```

[top](#index)