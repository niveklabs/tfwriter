# panos_panorama_gke_cluster

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    panos = ">= 1.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_panorama_gke_cluster" {
  source = "./modules/panos/r/panos_panorama_gke_cluster"

  # cluster_credential - (required) is a type of string
  cluster_credential = null
  # gcp_zone - (required) is a type of string
  gcp_zone = null
  # gke_cluster_group - (required) is a type of string
  gke_cluster_group = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "cluster_credential" {
  description = "(required)"
  type        = string
}

variable "gcp_zone" {
  description = "(required)"
  type        = string
}

variable "gke_cluster_group" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "panos_panorama_gke_cluster" "this" {
  # cluster_credential - (required) is a type of string
  cluster_credential = var.cluster_credential
  # gcp_zone - (required) is a type of string
  gcp_zone = var.gcp_zone
  # gke_cluster_group - (required) is a type of string
  gke_cluster_group = var.gke_cluster_group
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_panorama_gke_cluster.this.id
}

output "this" {
  value = panos_panorama_gke_cluster.this
}
```

[top](#index)