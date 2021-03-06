# constellix_a_record_pool

[back](../constellix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "constellix_a_record_pool" {
  source = "./modules/constellix/d/constellix_a_record_pool"

  # disable_flag_1 - (optional) is a type of bool
  disable_flag_1 = null
  # failed_flag - (optional) is a type of bool
  failed_flag = null
  # min_available_failover - (optional) is a type of number
  min_available_failover = null
  # name - (required) is a type of string
  name = null
  # note - (optional) is a type of string
  note = null
  # num_return - (optional) is a type of number
  num_return = null
  # version - (optional) is a type of number
  version = null

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
variable "disable_flag_1" {
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
  description = "(optional)"
  type        = number
  default     = null
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
  description = "(optional)"
  type        = number
  default     = null
}

variable "version" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "values" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      check_id     = number
      disable_flag = string
      policy       = string
      value        = string
      weight       = number
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "constellix_a_record_pool" "this" {
  # disable_flag_1 - (optional) is a type of bool
  disable_flag_1 = var.disable_flag_1
  # failed_flag - (optional) is a type of bool
  failed_flag = var.failed_flag
  # min_available_failover - (optional) is a type of number
  min_available_failover = var.min_available_failover
  # name - (required) is a type of string
  name = var.name
  # note - (optional) is a type of string
  note = var.note
  # num_return - (optional) is a type of number
  num_return = var.num_return
  # version - (optional) is a type of number
  version = var.version

  dynamic "values" {
    for_each = var.values
    content {
      # check_id - (optional) is a type of number
      check_id = values.value["check_id"]
      # disable_flag - (optional) is a type of string
      disable_flag = values.value["disable_flag"]
      # policy - (required) is a type of string
      policy = values.value["policy"]
      # value - (required) is a type of string
      value = values.value["value"]
      # weight - (required) is a type of number
      weight = values.value["weight"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "disable_flag_1" {
  description = "returns a bool"
  value       = data.constellix_a_record_pool.this.disable_flag_1
}

output "failed_flag" {
  description = "returns a bool"
  value       = data.constellix_a_record_pool.this.failed_flag
}

output "id" {
  description = "returns a string"
  value       = data.constellix_a_record_pool.this.id
}

output "min_available_failover" {
  description = "returns a number"
  value       = data.constellix_a_record_pool.this.min_available_failover
}

output "note" {
  description = "returns a string"
  value       = data.constellix_a_record_pool.this.note
}

output "num_return" {
  description = "returns a number"
  value       = data.constellix_a_record_pool.this.num_return
}

output "version" {
  description = "returns a number"
  value       = data.constellix_a_record_pool.this.version
}

output "this" {
  value = constellix_a_record_pool.this
}
```

[top](#index)