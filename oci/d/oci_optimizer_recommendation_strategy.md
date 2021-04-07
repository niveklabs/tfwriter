# oci_optimizer_recommendation_strategy

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
module "oci_optimizer_recommendation_strategy" {
  source = "./modules/oci/d/oci_optimizer_recommendation_strategy"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # compartment_id_in_subtree - (required) is a type of bool
  compartment_id_in_subtree = null
  # name - (optional) is a type of string
  name = null
  # recommendation_name - (optional) is a type of string
  recommendation_name = null
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

variable "recommendation_name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "oci_optimizer_recommendation_strategy" "this" {
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # compartment_id_in_subtree - (required) is a type of bool
  compartment_id_in_subtree = var.compartment_id_in_subtree
  # name - (optional) is a type of string
  name = var.name
  # recommendation_name - (optional) is a type of string
  recommendation_name = var.recommendation_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.oci_optimizer_recommendation_strategy.this.id
}

output "items" {
  description = "returns a list of object"
  value       = data.oci_optimizer_recommendation_strategy.this.items
}

output "this" {
  value = oci_optimizer_recommendation_strategy.this
}
```

[top](#index)