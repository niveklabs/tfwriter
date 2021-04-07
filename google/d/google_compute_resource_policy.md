# google_compute_resource_policy

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_compute_resource_policy" {
  source = "./modules/google/d/google_compute_resource_policy"

  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - The name of the resource, provided by the client when initially creating\nthe resource. The resource name must be 1-63 characters long, and comply\nwith RFC1035. Specifically, the name must be 1-63 characters long and\nmatch the regular expression '[a-z]([-a-z0-9]*[a-z0-9])'? which means the\nfirst character must be a lowercase letter, and all following characters\nmust be a dash, lowercase letter, or digit, except the last character,\nwhich cannot be a dash."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - Region where resource policy resides."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "google_compute_resource_policy" "this" {
  # name - (required) is a type of string
  name = var.name
  # project - (optional) is a type of string
  project = var.project
  # region - (optional) is a type of string
  region = var.region
}
```

[top](#index)

### Outputs

```terraform
output "group_placement_policy" {
  description = "returns a list of object"
  value       = data.google_compute_resource_policy.this.group_placement_policy
}

output "id" {
  description = "returns a string"
  value       = data.google_compute_resource_policy.this.id
}

output "self_link" {
  description = "returns a string"
  value       = data.google_compute_resource_policy.this.self_link
}

output "snapshot_schedule_policy" {
  description = "returns a list of object"
  value       = data.google_compute_resource_policy.this.snapshot_schedule_policy
}

output "this" {
  value = google_compute_resource_policy.this
}
```

[top](#index)