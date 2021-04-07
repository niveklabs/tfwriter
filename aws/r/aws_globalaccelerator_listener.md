# aws_globalaccelerator_listener

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_globalaccelerator_listener" {
  source = "./modules/aws/r/aws_globalaccelerator_listener"

  # accelerator_arn - (required) is a type of string
  accelerator_arn = null
  # client_affinity - (optional) is a type of string
  client_affinity = null
  # protocol - (required) is a type of string
  protocol = null

  port_range = [{
    from_port = null
    to_port   = null
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
variable "accelerator_arn" {
  description = "(required)"
  type        = string
}

variable "client_affinity" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "protocol" {
  description = "(required)"
  type        = string
}

variable "port_range" {
  description = "nested block: NestingSet, min items: 1, max items: 10"
  type = set(object(
    {
      from_port = number
      to_port   = number
    }
  ))
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
resource "aws_globalaccelerator_listener" "this" {
  # accelerator_arn - (required) is a type of string
  accelerator_arn = var.accelerator_arn
  # client_affinity - (optional) is a type of string
  client_affinity = var.client_affinity
  # protocol - (required) is a type of string
  protocol = var.protocol

  dynamic "port_range" {
    for_each = var.port_range
    content {
      # from_port - (optional) is a type of number
      from_port = port_range.value["from_port"]
      # to_port - (optional) is a type of number
      to_port = port_range.value["to_port"]
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
output "id" {
  description = "returns a string"
  value       = aws_globalaccelerator_listener.this.id
}

output "this" {
  value = aws_globalaccelerator_listener.this
}
```

[top](#index)