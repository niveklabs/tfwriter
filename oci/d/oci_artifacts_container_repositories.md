# oci_artifacts_container_repositories

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
module "oci_artifacts_container_repositories" {
  source = "./modules/oci/d/oci_artifacts_container_repositories"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # compartment_id_in_subtree - (optional) is a type of bool
  compartment_id_in_subtree = null
  # display_name - (optional) is a type of string
  display_name = null
  # is_public - (optional) is a type of bool
  is_public = null
  # repository_id - (optional) is a type of string
  repository_id = null
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

variable "is_public" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "repository_id" {
  description = "(optional)"
  type        = string
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
data "oci_artifacts_container_repositories" "this" {
  compartment_id            = var.compartment_id
  compartment_id_in_subtree = var.compartment_id_in_subtree
  display_name              = var.display_name
  is_public                 = var.is_public
  repository_id             = var.repository_id
  state                     = var.state

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
output "container_repository_collection" {
  description = "returns a list of object"
  value       = data.oci_artifacts_container_repositories.this.container_repository_collection
}

output "id" {
  description = "returns a string"
  value       = data.oci_artifacts_container_repositories.this.id
}

output "this" {
  value = oci_artifacts_container_repositories.this
}
```

[top](#index)