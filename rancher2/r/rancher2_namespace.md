# rancher2_namespace

[back](../rancher2.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    rancher2 = ">= 1.13.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "rancher2_namespace" {
  source = "./modules/rancher2/r/rancher2_namespace"

  # annotations - (optional) is a type of map of string
  annotations = {}
  # description - (optional) is a type of string
  description = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null
  # project_id - (required) is a type of string
  project_id = null
  # wait_for_cluster - (optional) is a type of bool
  wait_for_cluster = null

  container_resource_limit = [{
    limits_cpu      = null
    limits_memory   = null
    requests_cpu    = null
    requests_memory = null
  }]

  resource_quota = [{
    limit = [{
      config_maps              = null
      limits_cpu               = null
      limits_memory            = null
      persistent_volume_claims = null
      pods                     = null
      replication_controllers  = null
      requests_cpu             = null
      requests_memory          = null
      requests_storage         = null
      secrets                  = null
      services                 = null
      services_load_balancers  = null
      services_node_ports      = null
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
variable "annotations" {
  description = "(optional) - Annotations of the resource"
  type        = map(string)
  default     = null
}

variable "description" {
  description = "(optional) - Description of the k8s namespace managed by rancher v2"
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional) - Labels of the resource"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - Name of the k8s namespace managed by rancher v2"
  type        = string
}

variable "project_id" {
  description = "(required) - Project ID where k8s namespace belongs"
  type        = string
}

variable "wait_for_cluster" {
  description = "(optional) - Wait for cluster becomes active"
  type        = bool
  default     = null
}

variable "container_resource_limit" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      limits_cpu      = string
      limits_memory   = string
      requests_cpu    = string
      requests_memory = string
    }
  ))
  default = []
}

variable "resource_quota" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      limit = list(object(
        {
          config_maps              = string
          limits_cpu               = string
          limits_memory            = string
          persistent_volume_claims = string
          pods                     = string
          replication_controllers  = string
          requests_cpu             = string
          requests_memory          = string
          requests_storage         = string
          secrets                  = string
          services                 = string
          services_load_balancers  = string
          services_node_ports      = string
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
resource "rancher2_namespace" "this" {
  # annotations - (optional) is a type of map of string
  annotations = var.annotations
  # description - (optional) is a type of string
  description = var.description
  # labels - (optional) is a type of map of string
  labels = var.labels
  # name - (required) is a type of string
  name = var.name
  # project_id - (required) is a type of string
  project_id = var.project_id
  # wait_for_cluster - (optional) is a type of bool
  wait_for_cluster = var.wait_for_cluster

  dynamic "container_resource_limit" {
    for_each = var.container_resource_limit
    content {
      # limits_cpu - (optional) is a type of string
      limits_cpu = container_resource_limit.value["limits_cpu"]
      # limits_memory - (optional) is a type of string
      limits_memory = container_resource_limit.value["limits_memory"]
      # requests_cpu - (optional) is a type of string
      requests_cpu = container_resource_limit.value["requests_cpu"]
      # requests_memory - (optional) is a type of string
      requests_memory = container_resource_limit.value["requests_memory"]
    }
  }

  dynamic "resource_quota" {
    for_each = var.resource_quota
    content {

      dynamic "limit" {
        for_each = resource_quota.value.limit
        content {
          # config_maps - (optional) is a type of string
          config_maps = limit.value["config_maps"]
          # limits_cpu - (optional) is a type of string
          limits_cpu = limit.value["limits_cpu"]
          # limits_memory - (optional) is a type of string
          limits_memory = limit.value["limits_memory"]
          # persistent_volume_claims - (optional) is a type of string
          persistent_volume_claims = limit.value["persistent_volume_claims"]
          # pods - (optional) is a type of string
          pods = limit.value["pods"]
          # replication_controllers - (optional) is a type of string
          replication_controllers = limit.value["replication_controllers"]
          # requests_cpu - (optional) is a type of string
          requests_cpu = limit.value["requests_cpu"]
          # requests_memory - (optional) is a type of string
          requests_memory = limit.value["requests_memory"]
          # requests_storage - (optional) is a type of string
          requests_storage = limit.value["requests_storage"]
          # secrets - (optional) is a type of string
          secrets = limit.value["secrets"]
          # services - (optional) is a type of string
          services = limit.value["services"]
          # services_load_balancers - (optional) is a type of string
          services_load_balancers = limit.value["services_load_balancers"]
          # services_node_ports - (optional) is a type of string
          services_node_ports = limit.value["services_node_ports"]
        }
      }

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
output "annotations" {
  description = "returns a map of string"
  value       = rancher2_namespace.this.annotations
}

output "id" {
  description = "returns a string"
  value       = rancher2_namespace.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = rancher2_namespace.this.labels
}

output "this" {
  value = rancher2_namespace.this
}
```

[top](#index)