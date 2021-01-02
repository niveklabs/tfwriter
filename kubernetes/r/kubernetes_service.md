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
    kubernetes = ">= 1.13.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "kubernetes_service" {
  source = "./modules/kubernetes/r/kubernetes_service"


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

  dynamic "metadata" {
    for_each = var.metadata
    content {
      annotations   = metadata.value["annotations"]
      generate_name = metadata.value["generate_name"]
      labels        = metadata.value["labels"]
      name          = metadata.value["name"]
      namespace     = metadata.value["namespace"]
    }
  }

  dynamic "spec" {
    for_each = var.spec
    content {
      cluster_ip                  = spec.value["cluster_ip"]
      external_ips                = spec.value["external_ips"]
      external_name               = spec.value["external_name"]
      external_traffic_policy     = spec.value["external_traffic_policy"]
      health_check_node_port      = spec.value["health_check_node_port"]
      load_balancer_ip            = spec.value["load_balancer_ip"]
      load_balancer_source_ranges = spec.value["load_balancer_source_ranges"]
      publish_not_ready_addresses = spec.value["publish_not_ready_addresses"]
      selector                    = spec.value["selector"]
      session_affinity            = spec.value["session_affinity"]
      type                        = spec.value["type"]

      dynamic "port" {
        for_each = spec.value.port
        content {
          name        = port.value["name"]
          node_port   = port.value["node_port"]
          port        = port.value["port"]
          protocol    = port.value["protocol"]
          target_port = port.value["target_port"]
        }
      }

    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
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

output "load_balancer_ingress" {
  description = "returns a list of object"
  value       = kubernetes_service.this.load_balancer_ingress
}

output "this" {
  value = kubernetes_service.this
}
```

[top](#index)