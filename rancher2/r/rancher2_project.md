# rancher2_project

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
module "rancher2_project" {
  source = "./modules/rancher2/r/rancher2_project"

  # annotations - (optional) is a type of map of string
  annotations = {}
  # cluster_id - (required) is a type of string
  cluster_id = null
  # description - (optional) is a type of string
  description = null
  # enable_project_monitoring - (optional) is a type of bool
  enable_project_monitoring = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null
  # pod_security_policy_template_id - (optional) is a type of string
  pod_security_policy_template_id = null
  # wait_for_cluster - (optional) is a type of bool
  wait_for_cluster = null

  container_resource_limit = [{
    limits_cpu      = null
    limits_memory   = null
    requests_cpu    = null
    requests_memory = null
  }]

  project_monitoring_input = [{
    answers = {}
    version = null
  }]

  resource_quota = [{
    namespace_default_limit = [{
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
    project_limit = [{
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

variable "cluster_id" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable_project_monitoring" {
  description = "(optional) - Enable built-in project monitoring"
  type        = bool
  default     = null
}

variable "labels" {
  description = "(optional) - Labels of the resource"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "pod_security_policy_template_id" {
  description = "(optional)"
  type        = string
  default     = null
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

variable "project_monitoring_input" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      answers = map(string)
      version = string
    }
  ))
  default = []
}

variable "resource_quota" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      namespace_default_limit = list(object(
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
      project_limit = list(object(
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
resource "rancher2_project" "this" {
  # annotations - (optional) is a type of map of string
  annotations = var.annotations
  # cluster_id - (required) is a type of string
  cluster_id = var.cluster_id
  # description - (optional) is a type of string
  description = var.description
  # enable_project_monitoring - (optional) is a type of bool
  enable_project_monitoring = var.enable_project_monitoring
  # labels - (optional) is a type of map of string
  labels = var.labels
  # name - (required) is a type of string
  name = var.name
  # pod_security_policy_template_id - (optional) is a type of string
  pod_security_policy_template_id = var.pod_security_policy_template_id
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

  dynamic "project_monitoring_input" {
    for_each = var.project_monitoring_input
    content {
      # answers - (optional) is a type of map of string
      answers = project_monitoring_input.value["answers"]
      # version - (optional) is a type of string
      version = project_monitoring_input.value["version"]
    }
  }

  dynamic "resource_quota" {
    for_each = var.resource_quota
    content {

      dynamic "namespace_default_limit" {
        for_each = resource_quota.value.namespace_default_limit
        content {
          # config_maps - (optional) is a type of string
          config_maps = namespace_default_limit.value["config_maps"]
          # limits_cpu - (optional) is a type of string
          limits_cpu = namespace_default_limit.value["limits_cpu"]
          # limits_memory - (optional) is a type of string
          limits_memory = namespace_default_limit.value["limits_memory"]
          # persistent_volume_claims - (optional) is a type of string
          persistent_volume_claims = namespace_default_limit.value["persistent_volume_claims"]
          # pods - (optional) is a type of string
          pods = namespace_default_limit.value["pods"]
          # replication_controllers - (optional) is a type of string
          replication_controllers = namespace_default_limit.value["replication_controllers"]
          # requests_cpu - (optional) is a type of string
          requests_cpu = namespace_default_limit.value["requests_cpu"]
          # requests_memory - (optional) is a type of string
          requests_memory = namespace_default_limit.value["requests_memory"]
          # requests_storage - (optional) is a type of string
          requests_storage = namespace_default_limit.value["requests_storage"]
          # secrets - (optional) is a type of string
          secrets = namespace_default_limit.value["secrets"]
          # services - (optional) is a type of string
          services = namespace_default_limit.value["services"]
          # services_load_balancers - (optional) is a type of string
          services_load_balancers = namespace_default_limit.value["services_load_balancers"]
          # services_node_ports - (optional) is a type of string
          services_node_ports = namespace_default_limit.value["services_node_ports"]
        }
      }

      dynamic "project_limit" {
        for_each = resource_quota.value.project_limit
        content {
          # config_maps - (optional) is a type of string
          config_maps = project_limit.value["config_maps"]
          # limits_cpu - (optional) is a type of string
          limits_cpu = project_limit.value["limits_cpu"]
          # limits_memory - (optional) is a type of string
          limits_memory = project_limit.value["limits_memory"]
          # persistent_volume_claims - (optional) is a type of string
          persistent_volume_claims = project_limit.value["persistent_volume_claims"]
          # pods - (optional) is a type of string
          pods = project_limit.value["pods"]
          # replication_controllers - (optional) is a type of string
          replication_controllers = project_limit.value["replication_controllers"]
          # requests_cpu - (optional) is a type of string
          requests_cpu = project_limit.value["requests_cpu"]
          # requests_memory - (optional) is a type of string
          requests_memory = project_limit.value["requests_memory"]
          # requests_storage - (optional) is a type of string
          requests_storage = project_limit.value["requests_storage"]
          # secrets - (optional) is a type of string
          secrets = project_limit.value["secrets"]
          # services - (optional) is a type of string
          services = project_limit.value["services"]
          # services_load_balancers - (optional) is a type of string
          services_load_balancers = project_limit.value["services_load_balancers"]
          # services_node_ports - (optional) is a type of string
          services_node_ports = project_limit.value["services_node_ports"]
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
  value       = rancher2_project.this.annotations
}

output "id" {
  description = "returns a string"
  value       = rancher2_project.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = rancher2_project.this.labels
}

output "this" {
  value = rancher2_project.this
}
```

[top](#index)