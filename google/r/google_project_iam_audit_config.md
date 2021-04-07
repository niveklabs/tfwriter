# google_project_iam_audit_config

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "google_project_iam_audit_config" {
  source = "./modules/google/r/google_project_iam_audit_config"

  # project - (optional) is a type of string
  project = null
  # service - (required) is a type of string
  service = null

  audit_log_config = [{
    exempted_members = []
    log_type         = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service" {
  description = "(required) - Service which will be enabled for audit logging. The special value allServices covers all services."
  type        = string
}

variable "audit_log_config" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      exempted_members = set(string)
      log_type         = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "google_project_iam_audit_config" "this" {
  # project - (optional) is a type of string
  project = var.project
  # service - (required) is a type of string
  service = var.service

  dynamic "audit_log_config" {
    for_each = var.audit_log_config
    content {
      # exempted_members - (optional) is a type of set of string
      exempted_members = audit_log_config.value["exempted_members"]
      # log_type - (required) is a type of string
      log_type = audit_log_config.value["log_type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "etag" {
  description = "returns a string"
  value       = google_project_iam_audit_config.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_project_iam_audit_config.this.id
}

output "project" {
  description = "returns a string"
  value       = google_project_iam_audit_config.this.project
}

output "this" {
  value = google_project_iam_audit_config.this
}
```

[top](#index)