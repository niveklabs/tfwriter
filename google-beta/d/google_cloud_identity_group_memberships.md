# google_cloud_identity_group_memberships

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
module "google_cloud_identity_group_memberships" {
  source = "./modules/google-beta/d/google_cloud_identity_group_memberships"

  # group - (required) is a type of string
  group = null
}
```

[top](#index)

### Variables

```terraform
variable "group" {
  description = "(required) - The name of the Group to get memberships from."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "google_cloud_identity_group_memberships" "this" {
  group = var.group
}
```

[top](#index)

### Outputs

```terraform
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