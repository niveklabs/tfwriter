# nsxt_algorithm_type_ns_service

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
module "nsxt_algorithm_type_ns_service" {
  source = "./modules/nsxt/r/nsxt_algorithm_type_ns_service"

  # algorithm - (required) is a type of string
  algorithm = null
  # description - (optional) is a type of string
  description = null
  # destination_port - (required) is a type of string
  destination_port = null
  # display_name - (optional) is a type of string
  display_name = null
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
variable "algorithm" {
  description = "(required) - Algorithm"
  type        = string
}

variable "description" {
  description = "(optional) - Description of this resource"
  type        = string
  default     = null
}

variable "destination_port" {
  description = "(required) - A single destination port"
  type        = string
}

variable "display_name" {
  description = "(optional) - The display name of this resource. Defaults to ID if not set"
  type        = string
  default     = null
}

variable "source_ports" {
  description = "(optional) - Set of source ports or ranges"
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
resource "nsxt_algorithm_type_ns_service" "this" {
  # algorithm - (required) is a type of string
  algorithm = var.algorithm
  # description - (optional) is a type of string
  description = var.description
  # destination_port - (required) is a type of string
  destination_port = var.destination_port
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # source_ports - (optional) is a type of set of string
  source_ports = var.source_ports

  dynamic "tag" {
    for_each = var.tag
    content {
      # scope - (optional) is a type of string
      scope = tag.value["scope"]
      # tag - (optional) is a type of string
      tag = tag.value["tag"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "default_service" {
  description = "returns a bool"
  value       = nsxt_algorithm_type_ns_service.this.default_service
}

output "display_name" {
  description = "returns a string"
  value       = nsxt_algorithm_type_ns_service.this.display_name
}

output "id" {
  description = "returns a string"
  value       = nsxt_algorithm_type_ns_service.this.id
}

output "revision" {
  description = "returns a number"
  value       = nsxt_algorithm_type_ns_service.this.revision
}

output "this" {
  value = nsxt_algorithm_type_ns_service.this
}
```

[top](#index)