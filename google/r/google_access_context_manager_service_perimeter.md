# google_access_context_manager_service_perimeter

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
    google = ">= 3.62.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_access_context_manager_service_perimeter" {
  source = "./modules/google/r/google_access_context_manager_service_perimeter"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # parent - (required) is a type of string
  parent = null
  # perimeter_type - (optional) is a type of string
  perimeter_type = null
  # title - (required) is a type of string
  title = null
  # use_explicit_dry_run_spec - (optional) is a type of bool
  use_explicit_dry_run_spec = null

  spec = [{
    access_levels = []
    egress_policies = [{
      egress_from = [{
        identities    = []
        identity_type = null
      }]
      egress_to = [{
        operations = [{
          method_selectors = [{
            method     = null
            permission = null
          }]
          service_name = null
        }]
        resources = []
      }]
    }]
    ingress_policies = [{
      ingress_from = [{
        identities    = []
        identity_type = null
        sources = [{
          access_level = null
          resource     = null
        }]
      }]
      ingress_to = [{
        operations = [{
          method_selectors = [{
            method     = null
            permission = null
          }]
          service_name = null
        }]
        resources = []
      }]
    }]
    resources           = []
    restricted_services = []
    vpc_accessible_services = [{
      allowed_services   = []
      enable_restriction = null
    }]
  }]

  status = [{
    access_levels = []
    egress_policies = [{
      egress_from = [{
        identities    = []
        identity_type = null
      }]
      egress_to = [{
        operations = [{
          method_selectors = [{
            method     = null
            permission = null
          }]
          service_name = null
        }]
        resources = []
      }]
    }]
    ingress_policies = [{
      ingress_from = [{
        identities    = []
        identity_type = null
        sources = [{
          access_level = null
          resource     = null
        }]
      }]
      ingress_to = [{
        operations = [{
          method_selectors = [{
            method     = null
            permission = null
          }]
          service_name = null
        }]
        resources = []
      }]
    }]
    resources           = []
    restricted_services = []
    vpc_accessible_services = [{
      allowed_services   = []
      enable_restriction = null
    }]
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
variable "description" {
  description = "(optional) - Description of the ServicePerimeter and its use. Does not affect\nbehavior."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Resource name for the ServicePerimeter. The short_name component must\nbegin with a letter and only include alphanumeric and '_'.\nFormat: accessPolicies/{policy_id}/servicePerimeters/{short_name}"
  type        = string
}

variable "parent" {
  description = "(required) - The AccessPolicy this ServicePerimeter lives in.\nFormat: accessPolicies/{policy_id}"
  type        = string
}

variable "perimeter_type" {
  description = "(optional) - Specifies the type of the Perimeter. There are two types: regular and\nbridge. Regular Service Perimeter contains resources, access levels,\nand restricted services. Every resource can be in at most\nONE regular Service Perimeter.\n\nIn addition to being in a regular service perimeter, a resource can also\nbe in zero or more perimeter bridges. A perimeter bridge only contains\nresources. Cross project operations are permitted if all effected\nresources share some perimeter (whether bridge or regular). Perimeter\nBridge does not contain access levels or services: those are governed\nentirely by the regular perimeter that resource is in.\n\nPerimeter Bridges are typically useful when building more complex\ntopologies with many independent perimeters that need to share some data\nwith a common perimeter, but should not be able to share data among\nthemselves. Default value: \"PERIMETER_TYPE_REGULAR\" Possible values: [\"PERIMETER_TYPE_REGULAR\", \"PERIMETER_TYPE_BRIDGE\"]"
  type        = string
  default     = null
}

variable "title" {
  description = "(required) - Human readable title. Must be unique within the Policy."
  type        = string
}

variable "use_explicit_dry_run_spec" {
  description = "(optional) - Use explicit dry run spec flag. Ordinarily, a dry-run spec implicitly exists\nfor all Service Perimeters, and that spec is identical to the status for those\nService Perimeters. When this flag is set, it inhibits the generation of the\nimplicit spec, thereby allowing the user to explicitly provide a\nconfiguration (\"spec\") to use in a dry-run version of the Service Perimeter.\nThis allows the user to test changes to the enforced config (\"status\") without\nactually enforcing them. This testing is done through analyzing the differences\nbetween currently enforced and suggested restrictions. useExplicitDryRunSpec must\nbet set to True if any of the fields in the spec are set to non-default values."
  type        = bool
  default     = null
}

variable "spec" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      access_levels = list(string)
      egress_policies = list(object(
        {
          egress_from = list(object(
            {
              identities    = list(string)
              identity_type = string
            }
          ))
          egress_to = list(object(
            {
              operations = list(object(
                {
                  method_selectors = list(object(
                    {
                      method     = string
                      permission = string
                    }
                  ))
                  service_name = string
                }
              ))
              resources = list(string)
            }
          ))
        }
      ))
      ingress_policies = list(object(
        {
          ingress_from = list(object(
            {
              identities    = list(string)
              identity_type = string
              sources = list(object(
                {
                  access_level = string
                  resource     = string
                }
              ))
            }
          ))
          ingress_to = list(object(
            {
              operations = list(object(
                {
                  method_selectors = list(object(
                    {
                      method     = string
                      permission = string
                    }
                  ))
                  service_name = string
                }
              ))
              resources = list(string)
            }
          ))
        }
      ))
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
  default = []
}

variable "status" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      access_levels = list(string)
      egress_policies = list(object(
        {
          egress_from = list(object(
            {
              identities    = list(string)
              identity_type = string
            }
          ))
          egress_to = list(object(
            {
              operations = list(object(
                {
                  method_selectors = list(object(
                    {
                      method     = string
                      permission = string
                    }
                  ))
                  service_name = string
                }
              ))
              resources = list(string)
            }
          ))
        }
      ))
      ingress_policies = list(object(
        {
          ingress_from = list(object(
            {
              identities    = list(string)
              identity_type = string
              sources = list(object(
                {
                  access_level = string
                  resource     = string
                }
              ))
            }
          ))
          ingress_to = list(object(
            {
              operations = list(object(
                {
                  method_selectors = list(object(
                    {
                      method     = string
                      permission = string
                    }
                  ))
                  service_name = string
                }
              ))
              resources = list(string)
            }
          ))
        }
      ))
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
resource "google_access_context_manager_service_perimeter" "this" {
  description               = var.description
  name                      = var.name
  parent                    = var.parent
  perimeter_type            = var.perimeter_type
  title                     = var.title
  use_explicit_dry_run_spec = var.use_explicit_dry_run_spec

  dynamic "spec" {
    for_each = var.spec
    content {
      access_levels       = spec.value["access_levels"]
      resources           = spec.value["resources"]
      restricted_services = spec.value["restricted_services"]

      dynamic "egress_policies" {
        for_each = spec.value.egress_policies
        content {

          dynamic "egress_from" {
            for_each = egress_policies.value.egress_from
            content {
              identities    = egress_from.value["identities"]
              identity_type = egress_from.value["identity_type"]
            }
          }

          dynamic "egress_to" {
            for_each = egress_policies.value.egress_to
            content {
              resources = egress_to.value["resources"]

              dynamic "operations" {
                for_each = egress_to.value.operations
                content {
                  service_name = operations.value["service_name"]

                  dynamic "method_selectors" {
                    for_each = operations.value.method_selectors
                    content {
                      method     = method_selectors.value["method"]
                      permission = method_selectors.value["permission"]
                    }
                  }

                }
              }

            }
          }

        }
      }

      dynamic "ingress_policies" {
        for_each = spec.value.ingress_policies
        content {

          dynamic "ingress_from" {
            for_each = ingress_policies.value.ingress_from
            content {
              identities    = ingress_from.value["identities"]
              identity_type = ingress_from.value["identity_type"]

              dynamic "sources" {
                for_each = ingress_from.value.sources
                content {
                  access_level = sources.value["access_level"]
                  resource     = sources.value["resource"]
                }
              }

            }
          }

          dynamic "ingress_to" {
            for_each = ingress_policies.value.ingress_to
            content {
              resources = ingress_to.value["resources"]

              dynamic "operations" {
                for_each = ingress_to.value.operations
                content {
                  service_name = operations.value["service_name"]

                  dynamic "method_selectors" {
                    for_each = operations.value.method_selectors
                    content {
                      method     = method_selectors.value["method"]
                      permission = method_selectors.value["permission"]
                    }
                  }

                }
              }

            }
          }

        }
      }

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
    for_each = var.status
    content {
      access_levels       = status.value["access_levels"]
      resources           = status.value["resources"]
      restricted_services = status.value["restricted_services"]

      dynamic "egress_policies" {
        for_each = status.value.egress_policies
        content {

          dynamic "egress_from" {
            for_each = egress_policies.value.egress_from
            content {
              identities    = egress_from.value["identities"]
              identity_type = egress_from.value["identity_type"]
            }
          }

          dynamic "egress_to" {
            for_each = egress_policies.value.egress_to
            content {
              resources = egress_to.value["resources"]

              dynamic "operations" {
                for_each = egress_to.value.operations
                content {
                  service_name = operations.value["service_name"]

                  dynamic "method_selectors" {
                    for_each = operations.value.method_selectors
                    content {
                      method     = method_selectors.value["method"]
                      permission = method_selectors.value["permission"]
                    }
                  }

                }
              }

            }
          }

        }
      }

      dynamic "ingress_policies" {
        for_each = status.value.ingress_policies
        content {

          dynamic "ingress_from" {
            for_each = ingress_policies.value.ingress_from
            content {
              identities    = ingress_from.value["identities"]
              identity_type = ingress_from.value["identity_type"]

              dynamic "sources" {
                for_each = ingress_from.value.sources
                content {
                  access_level = sources.value["access_level"]
                  resource     = sources.value["resource"]
                }
              }

            }
          }

          dynamic "ingress_to" {
            for_each = ingress_policies.value.ingress_to
            content {
              resources = ingress_to.value["resources"]

              dynamic "operations" {
                for_each = ingress_to.value.operations
                content {
                  service_name = operations.value["service_name"]

                  dynamic "method_selectors" {
                    for_each = operations.value.method_selectors
                    content {
                      method     = method_selectors.value["method"]
                      permission = method_selectors.value["permission"]
                    }
                  }

                }
              }

            }
          }

        }
      }

      dynamic "vpc_accessible_services" {
        for_each = status.value.vpc_accessible_services
        content {
          allowed_services   = vpc_accessible_services.value["allowed_services"]
          enable_restriction = vpc_accessible_services.value["enable_restriction"]
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

```terraform
output "create_time" {
  description = "returns a string"
  value       = google_access_context_manager_service_perimeter.this.create_time
}

output "id" {
  description = "returns a string"
  value       = google_access_context_manager_service_perimeter.this.id
}

output "update_time" {
  description = "returns a string"
  value       = google_access_context_manager_service_perimeter.this.update_time
}

output "this" {
  value = google_access_context_manager_service_perimeter.this
}
```

[top](#index)