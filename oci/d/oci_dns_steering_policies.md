# oci_dns_steering_policies

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
    oci = ">= 4.20.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_dns_steering_policies" {
  source = "./modules/oci/d/oci_dns_steering_policies"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # display_name - (optional) is a type of string
  display_name = null
  # display_name_contains - (optional) is a type of string
  display_name_contains = null
  # health_check_monitor_id - (optional) is a type of string
  health_check_monitor_id = null
  # state - (optional) is a type of string
  state = null
  # template - (optional) is a type of string
  template = null
  # time_created_greater_than_or_equal_to - (optional) is a type of string
  time_created_greater_than_or_equal_to = null
  # time_created_less_than - (optional) is a type of string
  time_created_less_than = null

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
variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name_contains" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "health_check_monitor_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "time_created_greater_than_or_equal_to" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "time_created_less_than" {
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
data "oci_dns_steering_policies" "this" {
  compartment_id                        = var.compartment_id
  display_name                          = var.display_name
  display_name_contains                 = var.display_name_contains
  health_check_monitor_id               = var.health_check_monitor_id
  state                                 = var.state
  template                              = var.template
  time_created_greater_than_or_equal_to = var.time_created_greater_than_or_equal_to
  time_created_less_than                = var.time_created_less_than

  dynamic "filter" {
    for_each = var.filter
    content {
      name   = filter.value["name"]
      regex  = filter.value["regex"]
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
  value       = data.oci_dns_steering_policies.this.id
}

output "steering_policies" {
  description = "returns a list of object"
  value       = data.oci_dns_steering_policies.this.steering_policies
}

output "this" {
  value = oci_dns_steering_policies.this
}
```

[top](#index)