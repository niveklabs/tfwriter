# oci_containerengine_node_pool_option

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
module "oci_containerengine_node_pool_option" {
  source = "./modules/oci/d/oci_containerengine_node_pool_option"

  # compartment_id - (optional) is a type of string
  compartment_id = null
  # node_pool_option_id - (required) is a type of string
  node_pool_option_id = null
}
```

[top](#index)

### Variables

```terraform
variable "compartment_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "node_pool_option_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_containerengine_node_pool_option" "this" {
  # compartment_id - (optional) is a type of string
  compartment_id = var.compartment_id
  # node_pool_option_id - (required) is a type of string
  node_pool_option_id = var.node_pool_option_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.oci_containerengine_node_pool_option.this.id
}

output "images" {
  description = "returns a list of string"
  value       = data.oci_containerengine_node_pool_option.this.images
}

output "kubernetes_versions" {
  description = "returns a list of string"
  value       = data.oci_containerengine_node_pool_option.this.kubernetes_versions
}

output "shapes" {
  description = "returns a list of string"
  value       = data.oci_containerengine_node_pool_option.this.shapes
}

output "sources" {
  description = "returns a list of object"
  value       = data.oci_containerengine_node_pool_option.this.sources
}

output "this" {
  value = oci_containerengine_node_pool_option.this
}
```

[top](#index)