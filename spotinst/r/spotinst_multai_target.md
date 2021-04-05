# spotinst_multai_target

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
module "spotinst_multai_target" {
  source = "./modules/spotinst/r/spotinst_multai_target"

  # balancer_id - (required) is a type of string
  balancer_id = null
  # host - (required) is a type of string
  host = null
  # name - (optional) is a type of string
  name = null
  # port - (optional) is a type of number
  port = null
  # target_set_id - (required) is a type of string
  target_set_id = null
  # weight - (required) is a type of number
  weight = null

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

variable "host" {
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

variable "target_set_id" {
  description = "(required)"
  type        = string
}

variable "weight" {
  description = "(required)"
  type        = number
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
resource "spotinst_multai_target" "this" {
  balancer_id   = var.balancer_id
  host          = var.host
  name          = var.name
  port          = var.port
  target_set_id = var.target_set_id
  weight        = var.weight

  dynamic "tags" {
    for_each = var.tags
    content {
      key   = tags.value["key"]
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
  value       = spotinst_multai_target.this.id
}

output "this" {
  value = spotinst_multai_target.this
}
```

[top](#index)