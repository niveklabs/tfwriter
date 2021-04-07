# oci_health_checks_ping_probe_results

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_health_checks_ping_probe_results" {
  source = "./modules/oci/d/oci_health_checks_ping_probe_results"

  # probe_configuration_id - (required) is a type of string
  probe_configuration_id = null
  # start_time_greater_than_or_equal_to - (optional) is a type of number
  start_time_greater_than_or_equal_to = null
  # start_time_less_than_or_equal_to - (optional) is a type of number
  start_time_less_than_or_equal_to = null
  # target - (optional) is a type of string
  target = null

  filter = [{
    name   = null
    regex  = null
    values = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "probe_configuration_id" {
  description = "(required)"
  type        = string
}

variable "start_time_greater_than_or_equal_to" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "start_time_less_than_or_equal_to" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "target" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "filter" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name   = string
      regex  = bool
      values = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "oci_health_checks_ping_probe_results" "this" {
  # probe_configuration_id - (required) is a type of string
  probe_configuration_id = var.probe_configuration_id
  # start_time_greater_than_or_equal_to - (optional) is a type of number
  start_time_greater_than_or_equal_to = var.start_time_greater_than_or_equal_to
  # start_time_less_than_or_equal_to - (optional) is a type of number
  start_time_less_than_or_equal_to = var.start_time_less_than_or_equal_to
  # target - (optional) is a type of string
  target = var.target

  dynamic "filter" {
    for_each = var.filter
    content {
      # name - (required) is a type of string
      name = filter.value["name"]
      # regex - (optional) is a type of bool
      regex = filter.value["regex"]
      # values - (required) is a type of list of string
      values = filter.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.oci_health_checks_ping_probe_results.this.id
}

output "ping_probe_results" {
  description = "returns a list of object"
  value       = data.oci_health_checks_ping_probe_results.this.ping_probe_results
}

output "this" {
  value = oci_health_checks_ping_probe_results.this
}
```

[top](#index)