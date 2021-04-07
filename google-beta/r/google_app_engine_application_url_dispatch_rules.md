# google_app_engine_application_url_dispatch_rules

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
    google-beta = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_app_engine_application_url_dispatch_rules" {
  source = "./modules/google-beta/r/google_app_engine_application_url_dispatch_rules"

  # project - (optional) is a type of string
  project = null

  dispatch_rules = [{
    domain  = null
    path    = null
    service = null
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
variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dispatch_rules" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      domain  = string
      path    = string
      service = string
    }
  ))
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
resource "google_app_engine_application_url_dispatch_rules" "this" {
  # project - (optional) is a type of string
  project = var.project

  dynamic "dispatch_rules" {
    for_each = var.dispatch_rules
    content {
      # domain - (optional) is a type of string
      domain = dispatch_rules.value["domain"]
      # path - (required) is a type of string
      path = dispatch_rules.value["path"]
      # service - (required) is a type of string
      service = dispatch_rules.value["service"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
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
  value       = google_app_engine_application_url_dispatch_rules.this.id
}

output "project" {
  description = "returns a string"
  value       = google_app_engine_application_url_dispatch_rules.this.project
}

output "this" {
  value = google_app_engine_application_url_dispatch_rules.this
}
```

[top](#index)