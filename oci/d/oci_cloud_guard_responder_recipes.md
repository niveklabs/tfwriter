# oci_cloud_guard_responder_recipes

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
module "oci_cloud_guard_responder_recipes" {
  source = "./modules/oci/d/oci_cloud_guard_responder_recipes"

  # access_level - (optional) is a type of string
  access_level = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # compartment_id_in_subtree - (optional) is a type of bool
  compartment_id_in_subtree = null
  # display_name - (optional) is a type of string
  display_name = null
  # resource_metadata_only - (optional) is a type of bool
  resource_metadata_only = null
  # state - (optional) is a type of string
  state = null

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
variable "access_level" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "compartment_id_in_subtree" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_metadata_only" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "state" {
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
data "oci_cloud_guard_responder_recipes" "this" {
  # access_level - (optional) is a type of string
  access_level = var.access_level
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # compartment_id_in_subtree - (optional) is a type of bool
  compartment_id_in_subtree = var.compartment_id_in_subtree
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # resource_metadata_only - (optional) is a type of bool
  resource_metadata_only = var.resource_metadata_only
  # state - (optional) is a type of string
  state = var.state

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
  value       = data.oci_cloud_guard_responder_recipes.this.id
}

output "responder_recipe_collection" {
  description = "returns a list of object"
  value       = data.oci_cloud_guard_responder_recipes.this.responder_recipe_collection
}

output "this" {
  value = oci_cloud_guard_responder_recipes.this
}
```

[top](#index)