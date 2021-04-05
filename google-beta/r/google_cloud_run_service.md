# google_cloud_run_service

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
module "google_cloud_run_service" {
  source = "./modules/google-beta/r/google_cloud_run_service"

  # autogenerate_revision_name - (optional) is a type of bool
  autogenerate_revision_name = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null

  metadata = [{
    annotations      = {}
    generation       = null
    labels           = {}
    namespace        = null
    resource_version = null
    self_link        = null
    uid              = null
  }]

  template = [{
    metadata = [{
      annotations      = {}
      generation       = null
      labels           = {}
      name             = null
      namespace        = null
      resource_version = null
      self_link        = null
      uid              = null
    }]
    spec = [{
      container_concurrency = null
      containers = [{
        args    = []
        command = []
        env = [{
          name  = null
          value = null
        }]
        env_from = [{
          config_map_ref = [{
            local_object_reference = [{
              name = null
            }]
            optional = null
          }]
          prefix = null
          secret_ref = [{
            local_object_reference = [{
              name = null
            }]
            optional = null
          }]
        }]
        image = null
        ports = [{
          container_port = null
          name           = null
          protocol       = null
        }]
        resources = [{
          limits   = {}
          requests = {}
        }]
        working_dir = null
      }]
      service_account_name = null
      serving_state        = null
      timeout_seconds      = null
    }]
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]

  traffic = [{
    latest_revision = null
    percent         = null
    revision_name   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "autogenerate_revision_name" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "location" {
  description = "(required) - The location of the cloud run instance. eg us-central1"
  type        = string
}

variable "name" {
  description = "(required) - Name must be unique within a namespace, within a Cloud Run region.\nIs required when creating resources. Name is primarily intended\nfor creation idempotence and configuration definition. Cannot be updated.\nMore info: http://kubernetes.io/docs/user-guide/identifiers#names"
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "metadata" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      annotations      = map(string)
      generation       = number
      labels           = map(string)
      namespace        = string
      resource_version = string
      self_link        = string
      uid              = string
    }
  ))
  default = []
}

variable "template" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      metadata = list(object(
        {
          annotations      = map(string)
          generation       = number
          labels           = map(string)
          name             = string
          namespace        = string
          resource_version = string
          self_link        = string
          uid              = string
        }
      ))
      spec = list(object(
        {
          container_concurrency = number
          containers = list(object(
            {
              args    = list(string)
              command = list(string)
              env = list(object(
                {
                  name  = string
                  value = string
                }
              ))
              env_from = list(object(
                {
                  config_map_ref = list(object(
                    {
                      local_object_reference = list(object(
                        {
                          name = string
                        }
                      ))
                      optional = bool
                    }
                  ))
                  prefix = string
                  secret_ref = list(object(
                    {
                      local_object_reference = list(object(
                        {
                          name = string
                        }
                      ))
                      optional = bool
                    }
                  ))
                }
              ))
              image = string
              ports = list(object(
                {
                  container_port = number
                  name           = string
                  protocol       = string
                }
              ))
              resources = list(object(
                {
                  limits   = map(string)
                  requests = map(string)
                }
              ))
              working_dir = string
            }
          ))
          service_account_name = string
          serving_state        = string
          timeout_seconds      = number
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

variable "traffic" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      latest_revision = bool
      percent         = number
      revision_name   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_cloud_run_service" "this" {
  autogenerate_revision_name = var.autogenerate_revision_name
  location                   = var.location
  name                       = var.name
  project                    = var.project

  dynamic "metadata" {
    for_each = var.metadata
    content {
      annotations = metadata.value["annotations"]
      labels      = metadata.value["labels"]
      namespace   = metadata.value["namespace"]
    }
  }

  dynamic "template" {
    for_each = var.template
    content {

      dynamic "metadata" {
        for_each = template.value.metadata
        content {
          annotations = metadata.value["annotations"]
          labels      = metadata.value["labels"]
          name        = metadata.value["name"]
          namespace   = metadata.value["namespace"]
        }
      }

      dynamic "spec" {
        for_each = template.value.spec
        content {
          container_concurrency = spec.value["container_concurrency"]
          service_account_name  = spec.value["service_account_name"]
          timeout_seconds       = spec.value["timeout_seconds"]

          dynamic "containers" {
            for_each = spec.value.containers
            content {
              args        = containers.value["args"]
              command     = containers.value["command"]
              image       = containers.value["image"]
              working_dir = containers.value["working_dir"]

              dynamic "env" {
                for_each = containers.value.env
                content {
                  name  = env.value["name"]
                  value = env.value["value"]
                }
              }

              dynamic "env_from" {
                for_each = containers.value.env_from
                content {
                  prefix = env_from.value["prefix"]

                  dynamic "config_map_ref" {
                    for_each = env_from.value.config_map_ref
                    content {
                      optional = config_map_ref.value["optional"]

                      dynamic "local_object_reference" {
                        for_each = config_map_ref.value.local_object_reference
                        content {
                          name = local_object_reference.value["name"]
                        }
                      }

                    }
                  }

                  dynamic "secret_ref" {
                    for_each = env_from.value.secret_ref
                    content {
                      optional = secret_ref.value["optional"]

                      dynamic "local_object_reference" {
                        for_each = secret_ref.value.local_object_reference
                        content {
                          name = local_object_reference.value["name"]
                        }
                      }

                    }
                  }

                }
              }

              dynamic "ports" {
                for_each = containers.value.ports
                content {
                  container_port = ports.value["container_port"]
                  name           = ports.value["name"]
                  protocol       = ports.value["protocol"]
                }
              }

              dynamic "resources" {
                for_each = containers.value.resources
                content {
                  limits   = resources.value["limits"]
                  requests = resources.value["requests"]
                }
              }

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

  dynamic "traffic" {
    for_each = var.traffic
    content {
      latest_revision = traffic.value["latest_revision"]
      percent         = traffic.value["percent"]
      revision_name   = traffic.value["revision_name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = google_cloud_run_service.this.id
}

output "project" {
  description = "returns a string"
  value       = google_cloud_run_service.this.project
}

output "status" {
  description = "returns a list of object"
  value       = google_cloud_run_service.this.status
}

output "this" {
  value = google_cloud_run_service.this
}
```

[top](#index)