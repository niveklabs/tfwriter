# google_cloud_identity_group_memberships

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
module "google_cloud_identity_group_memberships" {
  source = "./modules/google/d/google_cloud_identity_group_memberships"

  # group - (required) is a type of string
  group = null
}
```

[top](#index)

### Variables

```hcl
variable "group" {
  description = "(required) - The name of the Group to get memberships from."
  type        = string
}
```

[top](#index)

### Datasource

```hcl
data "google_cloud_identity_group_memberships" "this" {
  group = var.group
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = data.google_cloud_identity_group_memberships.this.id
}

output "memberships" {
  description = "returns a list of object"
  value       = data.google_cloud_identity_group_memberships.this.memberships
}

output "this" {
  value = google_cloud_identity_group_memberships.this
}
```

[top](#index)