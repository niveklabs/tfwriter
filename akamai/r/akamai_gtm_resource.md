# akamai_gtm_resource

[back](../akamai.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    akamai = ">= 1.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "akamai_gtm_resource" {
  source = "./modules/akamai/r/akamai_gtm_resource"

  # aggregation_type - (required) is a type of string
  aggregation_type = null
  # constrained_property - (optional) is a type of string
  constrained_property = null
  # decay_rate - (optional) is a type of number
  decay_rate = null
  # description - (optional) is a type of string
  description = null
  # domain - (required) is a type of string
  domain = null
  # host_header - (optional) is a type of string
  host_header = null
  # leader_string - (optional) is a type of string
  leader_string = null
  # least_squares_decay - (optional) is a type of number
  least_squares_decay = null
  # load_imbalance_percentage - (optional) is a type of number
  load_imbalance_percentage = null
  # max_u_multiplicative_increment - (optional) is a type of number
  max_u_multiplicative_increment = null
  # name - (required) is a type of string
  name = null
  # type - (required) is a type of string
  type = null
  # upper_bound - (optional) is a type of number
  upper_bound = null
  # wait_on_complete - (optional) is a type of bool
  wait_on_complete = null

  resource_instance = [{
    datacenter_id           = null
    load_object             = null
    load_object_port        = null
    load_servers            = []
    use_default_load_object = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "aggregation_type" {
  description = "(required)"
  type        = string
}

variable "constrained_property" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "decay_rate" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "domain" {
  description = "(required)"
  type        = string
}

variable "host_header" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "leader_string" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "least_squares_decay" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "load_imbalance_percentage" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_u_multiplicative_increment" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "upper_bound" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "wait_on_complete" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "resource_instance" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      datacenter_id           = number
      load_object             = string
      load_object_port        = number
      load_servers            = list(string)
      use_default_load_object = bool
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "akamai_gtm_resource" "this" {
  aggregation_type               = var.aggregation_type
  constrained_property           = var.constrained_property
  decay_rate                     = var.decay_rate
  description                    = var.description
  domain                         = var.domain
  host_header                    = var.host_header
  leader_string                  = var.leader_string
  least_squares_decay            = var.least_squares_decay
  load_imbalance_percentage      = var.load_imbalance_percentage
  max_u_multiplicative_increment = var.max_u_multiplicative_increment
  name                           = var.name
  type                           = var.type
  upper_bound                    = var.upper_bound
  wait_on_complete               = var.wait_on_complete

  dynamic "resource_instance" {
    for_each = var.resource_instance
    content {
      datacenter_id           = resource_instance.value["datacenter_id"]
      load_object             = resource_instance.value["load_object"]
      load_object_port        = resource_instance.value["load_object_port"]
      load_servers            = resource_instance.value["load_servers"]
      use_default_load_object = resource_instance.value["use_default_load_object"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = akamai_gtm_resource.this.id
}

output "this" {
  value = akamai_gtm_resource.this
}
```

[top](#index)