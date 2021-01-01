# google_bigquery_dataset_access

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "google_bigquery_dataset_access" {
  source = "./modules/google/r/google_bigquery_dataset_access"

  # dataset_id - (required) is a type of string
  dataset_id = null
  # domain - (optional) is a type of string
  domain = null
  # group_by_email - (optional) is a type of string
  group_by_email = null
  # iam_member - (optional) is a type of string
  iam_member = null
  # project - (optional) is a type of string
  project = null
  # role - (optional) is a type of string
  role = null
  # special_group - (optional) is a type of string
  special_group = null
  # user_by_email - (optional) is a type of string
  user_by_email = null

  timeouts = [{
    create = null
    delete = null
  }]

  view = [{
    dataset_id = null
    project_id = null
    table_id   = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "dataset_id" {
  description = "(required) - A unique ID for this dataset, without the project name. The ID\nmust contain only letters (a-z, A-Z), numbers (0-9), or\nunderscores (_). The maximum length is 1,024 characters."
  type        = string
}

variable "domain" {
  description = "(optional) - A domain to grant access to. Any users signed in with the\ndomain specified will be granted the specified access"
  type        = string
  default     = null
}

variable "group_by_email" {
  description = "(optional) - An email address of a Google Group to grant access to."
  type        = string
  default     = null
}

variable "iam_member" {
  description = "(optional) - Some other type of member that appears in the IAM Policy but isn't a user,\ngroup, domain, or special group. For example: 'allUsers'"
  type        = string
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "role" {
  description = "(optional) - Describes the rights granted to the user specified by the other\nmember of the access object. Basic, predefined, and custom roles are\nsupported. Predefined roles that have equivalent basic roles are\nswapped by the API to their basic counterparts, and will show a diff\npost-create. See\n[official docs](https://cloud.google.com/bigquery/docs/access-control)."
  type        = string
  default     = null
}

variable "special_group" {
  description = "(optional) - A special group to grant access to. Possible values include:\n\n\n* 'projectOwners': Owners of the enclosing project.\n\n\n* 'projectReaders': Readers of the enclosing project.\n\n\n* 'projectWriters': Writers of the enclosing project.\n\n\n* 'allAuthenticatedUsers': All authenticated BigQuery users."
  type        = string
  default     = null
}

variable "user_by_email" {
  description = "(optional) - An email address of a user to grant access to. For example:\nfred@example.com"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
    }
  ))
  default = []
}

variable "view" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      dataset_id = string
      project_id = string
      table_id   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```hcl
resource "google_bigquery_dataset_access" "this" {
  dataset_id     = var.dataset_id
  domain         = var.domain
  group_by_email = var.group_by_email
  iam_member     = var.iam_member
  project        = var.project
  role           = var.role
  special_group  = var.special_group
  user_by_email  = var.user_by_email

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

  dynamic "view" {
    for_each = var.view
    content {
      dataset_id = view.value["dataset_id"]
      project_id = view.value["project_id"]
      table_id   = view.value["table_id"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "api_updated_member" {
  description = "returns a bool"
  value       = google_bigquery_dataset_access.this.api_updated_member
}

output "id" {
  description = "returns a string"
  value       = google_bigquery_dataset_access.this.id
}

output "project" {
  description = "returns a string"
  value       = google_bigquery_dataset_access.this.project
}

output "this" {
  value = google_bigquery_dataset_access.this
}
```

[top](#index)