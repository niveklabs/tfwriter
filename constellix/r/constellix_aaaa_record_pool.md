# constellix_aaaa_record_pool

[back](../constellix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    constellix = ">= 0.3.7"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "constellix_aaaa_record_pool" {
  source = "./modules/constellix/r/constellix_aaaa_record_pool"

  # disable_flag - (optional) is a type of bool
  disable_flag = null
  # failed_flag - (optional) is a type of bool
  failed_flag = null
  # min_available_failover - (required) is a type of number
  min_available_failover = null
  # name - (required) is a type of string
  name = null
  # note - (optional) is a type of string
  note = null
  # num_return - (required) is a type of number
  num_return = null

  values = [{
    check_id     = null
    disable_flag = null
    policy       = null
    value        = null
    weight       = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "disable_flag" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "failed_flag" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "min_available_failover" {
  description = "(required)"
  type        = number
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "note" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "num_return" {
  description = "(required)"
  type        = number
}

variable "values" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      check_id     = number
      disable_flag = string
      policy       = string
      value        = string
      weight       = number
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "constellix_aaaa_record_pool" "this" {
  disable_flag           = var.disable_flag
  failed_flag            = var.failed_flag
  min_available_failover = var.min_available_failover
  name                   = var.name
  note                   = var.note
  num_return             = var.num_return

  dynamic "values" {
    for_each = var.values
    content {
      check_id     = values.value["check_id"]
      disable_flag = values.value["disable_flag"]
      policy       = values.value["policy"]
      value        = values.value["value"]
      weight       = values.value["weight"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "disable_flag" {
  description = "returns a bool"
  value       = constellix_aaaa_record_pool.this.disable_flag
}

output "failed_flag" {
  description = "returns a bool"
  value       = constellix_aaaa_record_pool.this.failed_flag
}

output "id" {
  description = "returns a string"
  value       = constellix_aaaa_record_pool.this.id
}

output "note" {
  description = "returns a string"
  value       = constellix_aaaa_record_pool.this.note
}

output "this" {
  value = constellix_aaaa_record_pool.this
}
```

[top](#index)