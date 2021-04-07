# kubernetes_service

[back](../kubernetes.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    kubernetes = ">= 2.0.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "kubernetes_service" {
  source = "./modules/kubernetes/r/kubernetes_service"

  # wait_for_load_balancer - (optional) is a type of bool
  wait_for_load_balancer = null

  metadata = [{
    annotations      = {}
    generate_name    = null
    generation       = null
    labels           = {}
    name             = null
    namespace        = null
    resource_version = null
    self_link        = null
    uid              = null
  }]

  spec = [{
    cluster_ip                  = null
    external_ips                = []
    external_name               = null
    external_traffic_policy     = null
    health_check_node_port      = null
    load_balancer_ip            = null
    load_balancer_source_ranges = []
    port = [{
      name        = null
      node_port   = null
      port        = null
      protocol    = null
      target_port = null
    }]
    publish_not_ready_addresses = null
    selector                    = {}
    session_affinity            = null
    type                        = null
  }]

  timeouts = [{
    create = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "wait_for_load_balancer" {
  description = "(optional) - Terraform will wait for the load balancer to have at least 1 endpoint before considering the resource created."
  type        = bool
  default     = null
}

variable "metadata" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      annotations      = map(string)
      generate_name    = string
      generation       = number
      labels           = map(string)
      name             = string
      namespace        = string
      resource_version = string
      self_link        = string
      uid              = string
    }
  ))
}

variable "spec" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      cluster_ip                  = string
      external_ips                = set(string)
      external_name               = string
      external_traffic_policy     = string
      health_check_node_port      = number
      load_balancer_ip            = string
      load_balancer_source_ranges = set(string)
      port = list(object(
        {
          name        = string
          node_port   = number
          port        = number
          protocol    = string
          target_port = string
        }
      ))
      publish_not_ready_addresses = bool
      selector                    = map(string)
      session_affinity            = string
      type                        = string
    }
  ))
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "kubernetes_service" "this" {
  # wait_for_load_balancer - (optional) is a type of bool
  wait_for_load_balancer = var.wait_for_load_balancer

  dynamic "metadata" {
    for_each = var.metadata
    content {
      # annotations - (optional) is a type of map of string
      annotations = metadata.value["annotations"]
      # generate_name - (optional) is a type of string
      generate_name = metadata.value["generate_name"]
      # labels - (optional) is a type of map of string
      labels = metadata.value["labels"]
      # name - (optional) is a type of string
      name = metadata.value["name"]
      # namespace - (optional) is a type of string
      namespace = metadata.value["namespace"]
    }
  }

  dynamic "spec" {
    for_each = var.spec
    content {
      # cluster_ip - (optional) is a type of string
      cluster_ip = spec.value["cluster_ip"]
      # external_ips - (optional) is a type of set of string
      external_ips = spec.value["external_ips"]
      # external_name - (optional) is a type of string
      external_name = spec.value["external_name"]
      # external_traffic_policy - (optional) is a type of string
      external_traffic_policy = spec.value["external_traffic_policy"]
      # health_check_node_port - (optional) is a type of number
      health_check_node_port = spec.value["health_check_node_port"]
      # load_balancer_ip - (optional) is a type of string
      load_balancer_ip = spec.value["load_balancer_ip"]
      # load_balancer_source_ranges - (optional) is a type of set of string
      load_balancer_source_ranges = spec.value["load_balancer_source_ranges"]
      # publish_not_ready_addresses - (optional) is a type of bool
      publish_not_ready_addresses = spec.value["publish_not_ready_addresses"]
      # selector - (optional) is a type of map of string
      selector = spec.value["selector"]
      # session_affinity - (optional) is a type of string
      session_affinity = spec.value["session_affinity"]
      # type - (optional) is a type of string
      type = spec.value["type"]

      dynamic "port" {
        for_each = spec.value.port
        content {
          # name - (optional) is a type of string
          name = port.value["name"]
          # node_port - (optional) is a type of number
          node_port = port.value["node_port"]
          # port - (required) is a type of number
          port = port.value["port"]
          # protocol - (optional) is a type of string
          protocol = port.value["protocol"]
          # target_port - (optional) is a type of string
          target_port = port.value["target_port"]
        }
      }

    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = kubernetes_service.this.id
}

output "status" {
  description = "returns a list of object"
  value       = kubernetes_service.this.status
}

output "this" {
  value = kubernetes_service.this
}
```

[top](#index)