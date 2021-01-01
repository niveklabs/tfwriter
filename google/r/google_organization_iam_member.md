# google_organization_iam_member

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
module "google_organization_iam_member" {
  source = "./modules/google/r/google_organization_iam_member"

  # member - (required) is a type of string
  member = null
  # org_id - (required) is a type of string
  org_id = null
  # role - (required) is a type of string
  role = null

  condition = [{
    description = null
    expression  = null
    title       = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "member" {
  description = "(required)"
  type        = string
}

variable "org_id" {
  description = "(required) - The numeric ID of the organization in which you want to manage the audit logging config."
  type        = string
}

variable "role" {
  description = "(required)"
  type        = string
}

variable "condition" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      description = string
      expression  = string
      title       = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```hcl
resource "google_organization_iam_member" "this" {
  member = var.member
  org_id = var.org_id
  role   = var.role

  dynamic "condition" {
    for_each = var.condition
    content {
      description = condition.value["description"]
      expression  = condition.value["expression"]
      title       = condition.value["title"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "etag" {
  description = "returns a string"
  value       = google_organization_iam_member.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_organization_iam_member.this.id
}

output "this" {
  value = google_organization_iam_member.this
}
```

[top](#index)