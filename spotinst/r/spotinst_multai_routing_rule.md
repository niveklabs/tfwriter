# spotinst_multai_routing_rule

[back](../spotinst.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    spotinst = ">= 1.27.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "spotinst_multai_routing_rule" {
  source = "./modules/spotinst/r/spotinst_multai_routing_rule"

  # balancer_id - (required) is a type of string
  balancer_id = null
  # listener_id - (required) is a type of string
  listener_id = null
  # middleware_ids - (optional) is a type of list of string
  middleware_ids = []
  # priority - (optional) is a type of number
  priority = null
  # route - (required) is a type of string
  route = null
  # strategy - (optional) is a type of string
  strategy = null
  # target_set_ids - (required) is a type of list of string
  target_set_ids = []

  tags = [{
    key   = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "balancer_id" {
  description = "(required)"
  type        = string
}

variable "listener_id" {
  description = "(required)"
  type        = string
}

variable "middleware_ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "priority" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "route" {
  description = "(required)"
  type        = string
}

variable "strategy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "target_set_ids" {
  description = "(required)"
  type        = list(string)
}

variable "tags" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      key   = string
      value = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "spotinst_multai_routing_rule" "this" {
  # balancer_id - (required) is a type of string
  balancer_id = var.balancer_id
  # listener_id - (required) is a type of string
  listener_id = var.listener_id
  # middleware_ids - (optional) is a type of list of string
  middleware_ids = var.middleware_ids
  # priority - (optional) is a type of number
  priority = var.priority
  # route - (required) is a type of string
  route = var.route
  # strategy - (optional) is a type of string
  strategy = var.strategy
  # target_set_ids - (required) is a type of list of string
  target_set_ids = var.target_set_ids

  dynamic "tags" {
    for_each = var.tags
    content {
      # key - (required) is a type of string
      key = tags.value["key"]
      # value - (required) is a type of string
      value = tags.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = spotinst_multai_routing_rule.this.id
}

output "this" {
  value = spotinst_multai_routing_rule.this
}
```

[top](#index)