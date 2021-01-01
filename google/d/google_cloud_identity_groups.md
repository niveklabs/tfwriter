# google_cloud_identity_groups

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
module "google_cloud_identity_groups" {
  source = "./modules/google/d/google_cloud_identity_groups"

  # parent - (required) is a type of string
  parent = null
}
```

[top](#index)

### Variables

```hcl
variable "parent" {
  description = "(required) - The resource name of the entity under which this Group resides in the\nCloud Identity resource hierarchy.\n\nMust be of the form identitysources/{identity_source_id} for external-identity-mapped\ngroups or customers/{customer_id} for Google Groups."
  type        = string
}
```

[top](#index)

### Datasource

```hcl
data "google_cloud_identity_groups" "this" {
  parent = var.parent
}
```

[top](#index)

### Outputs

```hcl
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