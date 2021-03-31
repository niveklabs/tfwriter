# google_access_context_manager_service_perimeters

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

```terraform
variable "parent" {
  description = "(required) - The AccessPolicy this ServicePerimeter lives in.\nFormat: accessPolicies/{policy_id}"
  type        = string
}

variable "service_perimeters" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      create_time    = string
      description    = string
      name           = string
      perimeter_type = string
      spec = list(object(
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
      status = list(object(
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
      title                     = string
      update_time               = string
      use_explicit_dry_run_spec = bool
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
        for_each = service_perimeters.value.status
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
  value       = google_access_context_manager_service_perimeters.this.id
}

output "this" {
  value = google_access_context_manager_service_perimeters.this
}
```

[top](#index)