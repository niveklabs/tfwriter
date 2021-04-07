# oci_optimizer_histories

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
module "oci_optimizer_histories" {
  source = "./modules/oci/d/oci_optimizer_histories"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # compartment_id_in_subtree - (required) is a type of bool
  compartment_id_in_subtree = null
  # name - (optional) is a type of string
  name = null
  # recommendation_id - (optional) is a type of string
  recommendation_id = null
  # recommendation_name - (optional) is a type of string
  recommendation_name = null
  # resource_type - (optional) is a type of string
  resource_type = null
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

variable "compartment_id_in_subtree" {
  description = "(required)"
  type        = bool
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "recommendation_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "recommendation_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_type" {
  description = "(optional)"
  type        = string
  default     = null
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
data "oci_optimizer_histories" "this" {
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # compartment_id_in_subtree - (required) is a type of bool
  compartment_id_in_subtree = var.compartment_id_in_subtree
  # name - (optional) is a type of string
  name = var.name
  # recommendation_id - (optional) is a type of string
  recommendation_id = var.recommendation_id
  # recommendation_name - (optional) is a type of string
  recommendation_name = var.recommendation_name
  # resource_type - (optional) is a type of string
  resource_type = var.resource_type
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
output "history_collection" {
  description = "returns a list of object"
  value       = data.oci_optimizer_histories.this.history_collection
}

output "id" {
  description = "returns a string"
  value       = data.oci_optimizer_histories.this.id
}

output "this" {
  value = oci_optimizer_histories.this
}
```

[top](#index)