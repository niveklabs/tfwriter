# google_app_engine_domain_mapping

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
module "google_app_engine_domain_mapping" {
  source = "./modules/google-beta/r/google_app_engine_domain_mapping"

  # domain_name - (required) is a type of string
  domain_name = null
  # override_strategy - (optional) is a type of string
  override_strategy = null
  # project - (optional) is a type of string
  project = null

  ssl_settings = [{
    certificate_id                 = null
    pending_managed_certificate_id = null
    ssl_management_type            = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "domain_name" {
  description = "(required) - Relative name of the domain serving the application. Example: example.com."
  type        = string
}

variable "override_strategy" {
  description = "(optional) - Whether the domain creation should override any existing mappings for this domain.\nBy default, overrides are rejected. Default value: \"STRICT\" Possible values: [\"STRICT\", \"OVERRIDE\"]"
  type        = string
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_settings" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      certificate_id                 = string
      pending_managed_certificate_id = string
      ssl_management_type            = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_app_engine_domain_mapping" "this" {
  domain_name       = var.domain_name
  override_strategy = var.override_strategy
  project           = var.project

  dynamic "ssl_settings" {
    for_each = var.ssl_settings
    content {
      certificate_id      = ssl_settings.value["certificate_id"]
      ssl_management_type = ssl_settings.value["ssl_management_type"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = google_app_engine_domain_mapping.this.id
}

output "name" {
  description = "returns a string"
  value       = google_app_engine_domain_mapping.this.name
}

output "project" {
  description = "returns a string"
  value       = google_app_engine_domain_mapping.this.project
}

output "resource_records" {
  description = "returns a list of object"
  value       = google_app_engine_domain_mapping.this.resource_records
}

output "this" {
  value = google_app_engine_domain_mapping.this
}
```

[top](#index)