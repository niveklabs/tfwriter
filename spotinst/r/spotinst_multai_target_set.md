# spotinst_multai_target_set

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
module "spotinst_multai_target_set" {
  source = "./modules/spotinst/r/spotinst_multai_target_set"

  # balancer_id - (required) is a type of string
  balancer_id = null
  # deployment_id - (required) is a type of string
  deployment_id = null
  # name - (optional) is a type of string
  name = null
  # port - (optional) is a type of number
  port = null
  # protocol - (required) is a type of string
  protocol = null
  # weight - (required) is a type of number
  weight = null

  health_check = [{
    healthy_threshold   = null
    interval            = null
    path                = null
    port                = null
    protocol            = null
    timeout             = null
    unhealthy_threshold = null
  }]

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

variable "deployment_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "protocol" {
  description = "(required)"
  type        = string
}

variable "weight" {
  description = "(required)"
  type        = number
}

variable "health_check" {
  description = "nested block: NestingSet, min items: 1, max items: 1"
  type = set(object(
    {
      healthy_threshold   = number
      interval            = number
      path                = string
      port                = number
      protocol            = string
      timeout             = number
      unhealthy_threshold = number
    }
  ))
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
resource "spotinst_multai_target_set" "this" {
  # balancer_id - (required) is a type of string
  balancer_id = var.balancer_id
  # deployment_id - (required) is a type of string
  deployment_id = var.deployment_id
  # name - (optional) is a type of string
  name = var.name
  # port - (optional) is a type of number
  port = var.port
  # protocol - (required) is a type of string
  protocol = var.protocol
  # weight - (required) is a type of number
  weight = var.weight

  dynamic "health_check" {
    for_each = var.health_check
    content {
      # healthy_threshold - (required) is a type of number
      healthy_threshold = health_check.value["healthy_threshold"]
      # interval - (required) is a type of number
      interval = health_check.value["interval"]
      # path - (required) is a type of string
      path = health_check.value["path"]
      # port - (optional) is a type of number
      port = health_check.value["port"]
      # protocol - (required) is a type of string
      protocol = health_check.value["protocol"]
      # timeout - (required) is a type of number
      timeout = health_check.value["timeout"]
      # unhealthy_threshold - (required) is a type of number
      unhealthy_threshold = health_check.value["unhealthy_threshold"]
    }
  }

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
  value       = spotinst_multai_target_set.this.id
}

output "this" {
  value = spotinst_multai_target_set.this
}
```

[top](#index)