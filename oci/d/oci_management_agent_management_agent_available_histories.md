# oci_management_agent_management_agent_available_histories

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
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_management_agent_management_agent_available_histories" {
  source = "./modules/oci/d/oci_management_agent_management_agent_available_histories"

  # management_agent_id - (required) is a type of string
  management_agent_id = null
  # time_availability_status_ended_greater_than - (optional) is a type of string
  time_availability_status_ended_greater_than = null
  # time_availability_status_started_less_than - (optional) is a type of string
  time_availability_status_started_less_than = null

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
variable "management_agent_id" {
  description = "(required)"
  type        = string
}

variable "time_availability_status_ended_greater_than" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "time_availability_status_started_less_than" {
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
data "oci_management_agent_management_agent_available_histories" "this" {
  management_agent_id                         = var.management_agent_id
  time_availability_status_ended_greater_than = var.time_availability_status_ended_greater_than
  time_availability_status_started_less_than  = var.time_availability_status_started_less_than

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
output "availability_histories" {
  description = "returns a list of object"
  value       = data.oci_management_agent_management_agent_available_histories.this.availability_histories
}

output "id" {
  description = "returns a string"
  value       = data.oci_management_agent_management_agent_available_histories.this.id
}

output "this" {
  value = oci_management_agent_management_agent_available_histories.this
}
```

[top](#index)