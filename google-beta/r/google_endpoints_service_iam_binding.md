# google_endpoints_service_iam_binding

[back](../google-beta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "google_endpoints_service_iam_binding" {
  source = "./modules/google-beta/r/google_endpoints_service_iam_binding"

  # members - (required) is a type of set of string
  members = []
  # role - (required) is a type of string
  role = null
  # service_name - (required) is a type of string
  service_name = null

  condition = [{
    description = null
    expression  = null
    title       = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "members" {
  description = "(required)"
  type        = set(string)
}

variable "role" {
  description = "(required)"
  type        = string
}

variable "service_name" {
  description = "(required)"
  type        = string
}

variable "condition" {
  description = "nested block: NestingList, min items: 0, max items: 1"
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

```terraform
resource "google_endpoints_service_iam_binding" "this" {
  members      = var.members
  role         = var.role
  service_name = var.service_name

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

```terraform
output "etag" {
  description = "returns a string"
  value       = google_endpoints_service_iam_binding.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_endpoints_service_iam_binding.this.id
}

output "this" {
  value = google_endpoints_service_iam_binding.this
}
```

[top](#index)