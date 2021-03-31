# nsxt_l4_port_set_ns_service

[back](../nsxt.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nsxt = ">= 3.1.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nsxt_l4_port_set_ns_service" {
  source = "./modules/nsxt/r/nsxt_l4_port_set_ns_service"

  # description - (optional) is a type of string
  description = null
  # destination_ports - (optional) is a type of set of string
  destination_ports = []
  # display_name - (optional) is a type of string
  display_name = null
  # protocol - (required) is a type of string
  protocol = null
  # source_ports - (optional) is a type of set of string
  source_ports = []

  tag = [{
    scope = null
    tag   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description of this resource"
  type        = string
  default     = null
}

variable "destination_ports" {
  description = "(optional) - Set of destination ports"
  type        = set(string)
  default     = null
}

variable "display_name" {
  description = "(optional) - The display name of this resource. Defaults to ID if not set"
  type        = string
  default     = null
}

variable "protocol" {
  description = "(required) - L4 Protocol"
  type        = string
}

variable "source_ports" {
  description = "(optional) - Set of source ports"
  type        = set(string)
  default     = null
}

variable "tag" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      scope = string
      tag   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "nsxt_l4_port_set_ns_service" "this" {
  description       = var.description
  destination_ports = var.destination_ports
  display_name      = var.display_name
  protocol          = var.protocol
  source_ports      = var.source_ports

  dynamic "tag" {
    for_each = var.tag
    content {
      scope = tag.value["scope"]
      tag   = tag.value["tag"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "default_service" {
  description = "returns a bool"
  value       = nsxt_l4_port_set_ns_service.this.default_service
}

output "display_name" {
  description = "returns a string"
  value       = nsxt_l4_port_set_ns_service.this.display_name
}

output "id" {
  description = "returns a string"
  value       = nsxt_l4_port_set_ns_service.this.id
}

output "revision" {
  description = "returns a number"
  value       = nsxt_l4_port_set_ns_service.this.revision
}

output "this" {
  value = nsxt_l4_port_set_ns_service.this
}
```

[top](#index)