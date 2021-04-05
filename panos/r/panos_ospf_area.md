# panos_ospf_area

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    panos = ">= 1.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_ospf_area" {
  source = "./modules/panos/r/panos_ospf_area"

  # accept_summary - (optional) is a type of bool
  accept_summary = null
  # advertise_metric - (optional) is a type of number
  advertise_metric = null
  # advertise_type - (optional) is a type of string
  advertise_type = null
  # default_route_advertise - (optional) is a type of bool
  default_route_advertise = null
  # name - (required) is a type of string
  name = null
  # template - (optional) is a type of string
  template = null
  # template_stack - (optional) is a type of string
  template_stack = null
  # type - (optional) is a type of string
  type = null
  # virtual_router - (required) is a type of string
  virtual_router = null

  ext_range = [{
    action  = null
    network = null
  }]

  range = [{
    action  = null
    network = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "accept_summary" {
  description = "(optional) - (stub/nssa) Accept summary"
  type        = bool
  default     = null
}

variable "advertise_metric" {
  description = "(optional) - (stub/nssa) Advertise metric"
  type        = number
  default     = null
}

variable "advertise_type" {
  description = "(optional) - (nssa) Advertise type"
  type        = string
  default     = null
}

variable "default_route_advertise" {
  description = "(optional) - (stub/nssa) Default route advertise"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - Name"
  type        = string
}

variable "template" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_stack" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional) - Area type"
  type        = string
  default     = null
}

variable "virtual_router" {
  description = "(required) - The virtual router"
  type        = string
}

variable "ext_range" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action  = string
      network = string
    }
  ))
  default = []
}

variable "range" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action  = string
      network = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "panos_ospf_area" "this" {
  accept_summary          = var.accept_summary
  advertise_metric        = var.advertise_metric
  advertise_type          = var.advertise_type
  default_route_advertise = var.default_route_advertise
  name                    = var.name
  template                = var.template
  template_stack          = var.template_stack
  type                    = var.type
  virtual_router          = var.virtual_router

  dynamic "ext_range" {
    for_each = var.ext_range
    content {
      action  = ext_range.value["action"]
      network = ext_range.value["network"]
    }
  }

  dynamic "range" {
    for_each = var.range
    content {
      action  = range.value["action"]
      network = range.value["network"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_ospf_area.this.id
}

output "this" {
  value = panos_ospf_area.this
}
```

[top](#index)