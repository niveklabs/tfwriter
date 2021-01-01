# aws_globalaccelerator_listener

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
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
}
```

[top](#index)

### Variables

```hcl
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
  description = "nested mode: NestingSet, min items: 1, max items: 10"
  type = set(object(
    {
      from_port = number
      to_port   = number
    }
  ))
}
```

[top](#index)

### Resource

```hcl
resource "aws_globalaccelerator_listener" "this" {
  accelerator_arn = var.accelerator_arn
  client_affinity = var.client_affinity
  protocol        = var.protocol

  dynamic "port_range" {
    for_each = var.port_range
    content {
      from_port = port_range.value["from_port"]
      to_port   = port_range.value["to_port"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_globalaccelerator_listener.this.id
}

output "this" {
  value = aws_globalaccelerator_listener.this
}
```

[top](#index)