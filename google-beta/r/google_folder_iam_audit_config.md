# google_folder_iam_audit_config

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
module "google_folder_iam_audit_config" {
  source = "./modules/google-beta/r/google_folder_iam_audit_config"

  # folder - (required) is a type of string
  folder = null
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
variable "folder" {
  description = "(required)"
  type        = string
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
resource "google_folder_iam_audit_config" "this" {
  folder  = var.folder
  service = var.service

  dynamic "audit_log_config" {
    for_each = var.audit_log_config
    content {
      exempted_members = audit_log_config.value["exempted_members"]
      log_type         = audit_log_config.value["log_type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "etag" {
  description = "returns a string"
  value       = google_folder_iam_audit_config.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_folder_iam_audit_config.this.id
}

output "this" {
  value = google_folder_iam_audit_config.this
}
```

[top](#index)