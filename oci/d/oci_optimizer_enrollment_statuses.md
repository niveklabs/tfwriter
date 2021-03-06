# oci_optimizer_enrollment_statuses

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
module "oci_optimizer_enrollment_statuses" {
  source = "./modules/oci/d/oci_optimizer_enrollment_statuses"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # state - (optional) is a type of string
  state = null
  # status - (optional) is a type of string
  status = null

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

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
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
data "oci_optimizer_enrollment_statuses" "this" {
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # state - (optional) is a type of string
  state = var.state
  # status - (optional) is a type of string
  status = var.status

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
output "enrollment_status_collection" {
  description = "returns a list of object"
  value       = data.oci_optimizer_enrollment_statuses.this.enrollment_status_collection
}

output "id" {
  description = "returns a string"
  value       = data.oci_optimizer_enrollment_statuses.this.id
}

output "this" {
  value = oci_optimizer_enrollment_statuses.this
}
```

[top](#index)