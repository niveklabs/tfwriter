# oci_containerengine_cluster_kube_config

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
module "oci_containerengine_cluster_kube_config" {
  source = "./modules/oci/d/oci_containerengine_cluster_kube_config"

  # cluster_id - (required) is a type of string
  cluster_id = null
  # endpoint - (optional) is a type of string
  endpoint = null
  # expiration - (optional) is a type of number
  expiration = null
  # token_version - (optional) is a type of string
  token_version = null
}
```

[top](#index)

### Variables

```terraform
variable "cluster_id" {
  description = "(required)"
  type        = string
}

variable "endpoint" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "expiration" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "token_version" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "oci_containerengine_cluster_kube_config" "this" {
  cluster_id    = var.cluster_id
  endpoint      = var.endpoint
  expiration    = var.expiration
  token_version = var.token_version
}
```

[top](#index)

### Outputs

```terraform
output "content" {
  description = "returns a string"
  value       = data.oci_containerengine_cluster_kube_config.this.content
}

output "id" {
  description = "returns a string"
  value       = data.oci_containerengine_cluster_kube_config.this.id
}

output "this" {
  value = oci_containerengine_cluster_kube_config.this
}
```

[top](#index)