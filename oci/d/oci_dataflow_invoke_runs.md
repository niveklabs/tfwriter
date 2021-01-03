# oci_dataflow_invoke_runs

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
    oci = ">= 4.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_dataflow_invoke_runs" {
  source = "./modules/oci/d/oci_dataflow_invoke_runs"

  # application_id - (optional) is a type of string
  application_id = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # display_name - (optional) is a type of string
  display_name = null
  # display_name_starts_with - (optional) is a type of string
  display_name_starts_with = null
  # owner_principal_id - (optional) is a type of string
  owner_principal_id = null
  # state - (optional) is a type of string
  state = null
  # time_created_greater_than - (optional) is a type of string
  time_created_greater_than = null

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
variable "application_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name_starts_with" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "owner_principal_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "time_created_greater_than" {
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
data "oci_dataflow_invoke_runs" "this" {
  application_id            = var.application_id
  compartment_id            = var.compartment_id
  display_name              = var.display_name
  display_name_starts_with  = var.display_name_starts_with
  owner_principal_id        = var.owner_principal_id
  state                     = var.state
  time_created_greater_than = var.time_created_greater_than

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
  value       = data.oci_dataflow_invoke_runs.this.id
}

output "runs" {
  description = "returns a list of object"
  value       = data.oci_dataflow_invoke_runs.this.runs
}

output "this" {
  value = oci_dataflow_invoke_runs.this
}
```

[top](#index)