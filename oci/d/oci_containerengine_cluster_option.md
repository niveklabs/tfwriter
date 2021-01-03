# oci_containerengine_cluster_option

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
module "oci_containerengine_cluster_option" {
  source = "./modules/oci/d/oci_containerengine_cluster_option"

  # cluster_option_id - (required) is a type of string
  cluster_option_id = null
  # compartment_id - (optional) is a type of string
  compartment_id = null
}
```

[top](#index)

### Variables

```terraform
variable "cluster_option_id" {
  description = "(required)"
  type        = string
}

variable "compartment_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "oci_containerengine_cluster_option" "this" {
  cluster_option_id = var.cluster_option_id
  compartment_id    = var.compartment_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.oci_containerengine_cluster_option.this.id
}

output "kubernetes_versions" {
  description = "returns a list of string"
  value       = data.oci_containerengine_cluster_option.this.kubernetes_versions
}

output "this" {
  value = oci_containerengine_cluster_option.this
}
```

[top](#index)