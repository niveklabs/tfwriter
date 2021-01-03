# fortios_switchcontrollerqos_queuepolicy

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_switchcontrollerqos_queuepolicy" {
  source = "./modules/fortios/r/fortios_switchcontrollerqos_queuepolicy"

  # name - (required) is a type of string
  name = null
  # rate_by - (required) is a type of string
  rate_by = null
  # schedule - (required) is a type of string
  schedule = null

  cos_queue = [{
    description      = null
    drop_policy      = null
    max_rate         = null
    max_rate_percent = null
    min_rate         = null
    min_rate_percent = null
    name             = null
    weight           = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "rate_by" {
  description = "(required)"
  type        = string
}

variable "schedule" {
  description = "(required)"
  type        = string
}

variable "cos_queue" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      description      = string
      drop_policy      = string
      max_rate         = number
      max_rate_percent = number
      min_rate         = number
      min_rate_percent = number
      name             = string
      weight           = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_switchcontrollerqos_queuepolicy" "this" {
  name     = var.name
  rate_by  = var.rate_by
  schedule = var.schedule

  dynamic "cos_queue" {
    for_each = var.cos_queue
    content {
      description      = cos_queue.value["description"]
      drop_policy      = cos_queue.value["drop_policy"]
      max_rate         = cos_queue.value["max_rate"]
      max_rate_percent = cos_queue.value["max_rate_percent"]
      min_rate         = cos_queue.value["min_rate"]
      min_rate_percent = cos_queue.value["min_rate_percent"]
      name             = cos_queue.value["name"]
      weight           = cos_queue.value["weight"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_switchcontrollerqos_queuepolicy.this.id
}

output "this" {
  value = fortios_switchcontrollerqos_queuepolicy.this
}
```

[top](#index)