# google_access_context_manager_service_perimeters

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
module "google_access_context_manager_service_perimeters" {
  source = "./modules/google/r/google_access_context_manager_service_perimeters"

  # parent - (required) is a type of string
  parent = null

  service_perimeters = [{
    create_time    = null
    description    = null
    name           = null
    perimeter_type = null
    spec = [{
      access_levels       = []
      resources           = []
      restricted_services = []
      vpc_accessible_services = [{
        allowed_services   = []
        enable_restriction = null
      }]
    }]
    status = [{
      access_levels       = []
      resources           = []
      restricted_services = []
      vpc_accessible_services = [{
        allowed_services   = []
        enable_restriction = null
      }]
    }]
    title                     = null
    update_time               = null
    use_explicit_dry_run_spec = null
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

```hcl
variable "parent" {
  description = "(required) - The AccessPolicy this ServicePerimeter lives in.\nFormat: accessPolicies/{policy_id}"
  type        = string
}

variable "service_perimeters" {
  description = "nested mode: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      create_time    = string
      description    = string
      name           = string
      perimeter_type = string
      spec = list(object(
        {
          access_levels       = list(string)
          resources           = list(string)
          restricted_services = list(string)
          vpc_accessible_services = list(object(
            {
              allowed_services   = list(string)
              enable_restriction = bool
            }
          ))
        }
      ))
      status = list(object(
        {
          access_levels       = list(string)
          resources           = list(string)
          restricted_services = set(string)
          vpc_accessible_services = list(object(
            {
              allowed_services   = set(string)
              enable_restriction = bool
            }
          ))
        }
      ))
      title                     = string
      update_time               = string
      use_explicit_dry_run_spec = bool
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
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

```hcl
resource "google_access_context_manager_service_perimeters" "this" {
  parent = var.parent

  dynamic "service_perimeters" {
    for_each = var.service_perimeters
    content {
      description               = service_perimeters.value["description"]
      name                      = service_perimeters.value["name"]
      perimeter_type            = service_perimeters.value["perimeter_type"]
      title                     = service_perimeters.value["title"]
      use_explicit_dry_run_spec = service_perimeters.value["use_explicit_dry_run_spec"]

      dynamic "spec" {
        for_each = service_perimeters.value.spec
        content {
          access_levels       = spec.value["access_levels"]
          resources           = spec.value["resources"]
          restricted_services = spec.value["restricted_services"]

          dynamic "vpc_accessible_services" {
            for_each = spec.value.vpc_accessible_services
            content {
              allowed_services   = vpc_accessible_services.value["allowed_services"]
              enable_restriction = vpc_accessible_services.value["enable_restriction"]
            }
          }

        }
      }

      dynamic "status" {
        for_each = service_perimeters.value.status
        content {
          access_levels       = status.value["access_levels"]
          resources           = status.value["resources"]
          restricted_services = status.value["restricted_services"]

          dynamic "vpc_accessible_services" {
            for_each = status.value.vpc_accessible_services
            content {
              allowed_services   = vpc_accessible_services.value["allowed_services"]
              enable_restriction = vpc_accessible_services.value["enable_restriction"]
            }
          }

        }
      }

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

```hcl
output "id" {
  description = "returns a string"
  value       = google_access_context_manager_service_perimeters.this.id
}

output "this" {
  value = google_access_context_manager_service_perimeters.this
}
```

[top](#index)