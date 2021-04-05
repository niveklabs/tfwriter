# stackpath_compute_network_policy

[back](../stackpath.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    stackpath = ">= 1.3.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "stackpath_compute_network_policy" {
  source = "./modules/stackpath/r/stackpath_compute_network_policy"

  # annotations - (optional) is a type of map of string
  annotations = {}
  # description - (optional) is a type of string
  description = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null
  # policy_types - (required) is a type of list of string
  policy_types = []
  # priority - (required) is a type of number
  priority = null
  # slug - (required) is a type of string
  slug = null

  egress = [{
    action      = null
    description = null
    protocol = [{
      ah = [{

      }]
      esp = [{

      }]
      gre = [{

      }]
      icmp = [{

      }]
      tcp = [{
        destination_ports = []
        source_ports      = []
      }]
      tcp_udp = [{
        destination_ports = []
        source_ports      = []
      }]
      udp = [{
        destination_ports = []
        source_ports      = []
      }]
    }]
    to = [{
      instance_selector = [{
        key      = null
        operator = null
        values   = []
      }]
      ip_block = [{
        cidr   = null
        except = []
      }]
      network_selector = [{
        key      = null
        operator = null
        values   = []
      }]
    }]
  }]

  ingress = [{
    action      = null
    description = null
    from = [{
      instance_selector = [{
        key      = null
        operator = null
        values   = []
      }]
      ip_block = [{
        cidr   = null
        except = []
      }]
      network_selector = [{
        key      = null
        operator = null
        values   = []
      }]
    }]
    protocol = [{
      ah = [{

      }]
      esp = [{

      }]
      gre = [{

      }]
      icmp = [{

      }]
      tcp = [{
        destination_ports = []
        source_ports      = []
      }]
      tcp_udp = [{
        destination_ports = []
        source_ports      = []
      }]
      udp = [{
        destination_ports = []
        source_ports      = []
      }]
    }]
  }]

  instance_selector = [{
    key      = null
    operator = null
    values   = []
  }]

  network_selector = [{
    key      = null
    operator = null
    values   = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "annotations" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "policy_types" {
  description = "(required)"
  type        = list(string)
}

variable "priority" {
  description = "(required)"
  type        = number
}

variable "slug" {
  description = "(required)"
  type        = string
}

variable "egress" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action      = string
      description = string
      protocol = list(object(
        {
          ah = list(object(
            {

            }
          ))
          esp = list(object(
            {

            }
          ))
          gre = list(object(
            {

            }
          ))
          icmp = list(object(
            {

            }
          ))
          tcp = list(object(
            {
              destination_ports = list(string)
              source_ports      = list(string)
            }
          ))
          tcp_udp = list(object(
            {
              destination_ports = list(string)
              source_ports      = list(string)
            }
          ))
          udp = list(object(
            {
              destination_ports = list(string)
              source_ports      = list(string)
            }
          ))
        }
      ))
      to = list(object(
        {
          instance_selector = list(object(
            {
              key      = string
              operator = string
              values   = list(string)
            }
          ))
          ip_block = list(object(
            {
              cidr   = string
              except = list(string)
            }
          ))
          network_selector = list(object(
            {
              key      = string
              operator = string
              values   = list(string)
            }
          ))
        }
      ))
    }
  ))
  default = []
}

variable "ingress" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action      = string
      description = string
      from = list(object(
        {
          instance_selector = list(object(
            {
              key      = string
              operator = string
              values   = list(string)
            }
          ))
          ip_block = list(object(
            {
              cidr   = string
              except = list(string)
            }
          ))
          network_selector = list(object(
            {
              key      = string
              operator = string
              values   = list(string)
            }
          ))
        }
      ))
      protocol = list(object(
        {
          ah = list(object(
            {

            }
          ))
          esp = list(object(
            {

            }
          ))
          gre = list(object(
            {

            }
          ))
          icmp = list(object(
            {

            }
          ))
          tcp = list(object(
            {
              destination_ports = list(string)
              source_ports      = list(string)
            }
          ))
          tcp_udp = list(object(
            {
              destination_ports = list(string)
              source_ports      = list(string)
            }
          ))
          udp = list(object(
            {
              destination_ports = list(string)
              source_ports      = list(string)
            }
          ))
        }
      ))
    }
  ))
  default = []
}

variable "instance_selector" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      key      = string
      operator = string
      values   = list(string)
    }
  ))
  default = []
}

variable "network_selector" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      key      = string
      operator = string
      values   = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "stackpath_compute_network_policy" "this" {
  annotations  = var.annotations
  description  = var.description
  labels       = var.labels
  name         = var.name
  policy_types = var.policy_types
  priority     = var.priority
  slug         = var.slug

  dynamic "egress" {
    for_each = var.egress
    content {
      action      = egress.value["action"]
      description = egress.value["description"]

      dynamic "protocol" {
        for_each = egress.value.protocol
        content {

          dynamic "ah" {
            for_each = protocol.value.ah
            content {
            }
          }

          dynamic "esp" {
            for_each = protocol.value.esp
            content {
            }
          }

          dynamic "gre" {
            for_each = protocol.value.gre
            content {
            }
          }

          dynamic "icmp" {
            for_each = protocol.value.icmp
            content {
            }
          }

          dynamic "tcp" {
            for_each = protocol.value.tcp
            content {
              destination_ports = tcp.value["destination_ports"]
              source_ports      = tcp.value["source_ports"]
            }
          }

          dynamic "tcp_udp" {
            for_each = protocol.value.tcp_udp
            content {
              destination_ports = tcp_udp.value["destination_ports"]
              source_ports      = tcp_udp.value["source_ports"]
            }
          }

          dynamic "udp" {
            for_each = protocol.value.udp
            content {
              destination_ports = udp.value["destination_ports"]
              source_ports      = udp.value["source_ports"]
            }
          }

        }
      }

      dynamic "to" {
        for_each = egress.value.to
        content {

          dynamic "instance_selector" {
            for_each = to.value.instance_selector
            content {
              key      = instance_selector.value["key"]
              operator = instance_selector.value["operator"]
              values   = instance_selector.value["values"]
            }
          }

          dynamic "ip_block" {
            for_each = to.value.ip_block
            content {
              cidr   = ip_block.value["cidr"]
              except = ip_block.value["except"]
            }
          }

          dynamic "network_selector" {
            for_each = to.value.network_selector
            content {
              key      = network_selector.value["key"]
              operator = network_selector.value["operator"]
              values   = network_selector.value["values"]
            }
          }

        }
      }

    }
  }

  dynamic "ingress" {
    for_each = var.ingress
    content {
      action      = ingress.value["action"]
      description = ingress.value["description"]

      dynamic "from" {
        for_each = ingress.value.from
        content {

          dynamic "instance_selector" {
            for_each = from.value.instance_selector
            content {
              key      = instance_selector.value["key"]
              operator = instance_selector.value["operator"]
              values   = instance_selector.value["values"]
            }
          }

          dynamic "ip_block" {
            for_each = from.value.ip_block
            content {
              cidr   = ip_block.value["cidr"]
              except = ip_block.value["except"]
            }
          }

          dynamic "network_selector" {
            for_each = from.value.network_selector
            content {
              key      = network_selector.value["key"]
              operator = network_selector.value["operator"]
              values   = network_selector.value["values"]
            }
          }

        }
      }

      dynamic "protocol" {
        for_each = ingress.value.protocol
        content {

          dynamic "ah" {
            for_each = protocol.value.ah
            content {
            }
          }

          dynamic "esp" {
            for_each = protocol.value.esp
            content {
            }
          }

          dynamic "gre" {
            for_each = protocol.value.gre
            content {
            }
          }

          dynamic "icmp" {
            for_each = protocol.value.icmp
            content {
            }
          }

          dynamic "tcp" {
            for_each = protocol.value.tcp
            content {
              destination_ports = tcp.value["destination_ports"]
              source_ports      = tcp.value["source_ports"]
            }
          }

          dynamic "tcp_udp" {
            for_each = protocol.value.tcp_udp
            content {
              destination_ports = tcp_udp.value["destination_ports"]
              source_ports      = tcp_udp.value["source_ports"]
            }
          }

          dynamic "udp" {
            for_each = protocol.value.udp
            content {
              destination_ports = udp.value["destination_ports"]
              source_ports      = udp.value["source_ports"]
            }
          }

        }
      }

    }
  }

  dynamic "instance_selector" {
    for_each = var.instance_selector
    content {
      key      = instance_selector.value["key"]
      operator = instance_selector.value["operator"]
      values   = instance_selector.value["values"]
    }
  }

  dynamic "network_selector" {
    for_each = var.network_selector
    content {
      key      = network_selector.value["key"]
      operator = network_selector.value["operator"]
      values   = network_selector.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = stackpath_compute_network_policy.this.id
}

output "version" {
  description = "returns a string"
  value       = stackpath_compute_network_policy.this.version
}

output "this" {
  value = stackpath_compute_network_policy.this
}
```

[top](#index)