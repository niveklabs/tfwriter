# linode_object_storage_cluster

[back](../linode.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    linode = ">= 1.13.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "linode_object_storage_cluster" {
  source = "./modules/linode/d/linode_object_storage_cluster"

  # domain - (optional) is a type of string
  domain = null
  # region - (optional) is a type of string
  region = null
  # static_site_domain - (optional) is a type of string
  static_site_domain = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "domain" {
  description = "(optional) - The base URL for this cluster."
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - The region this cluster is located in."
  type        = string
  default     = null
}

variable "static_site_domain" {
  description = "(optional) - The base URL for this cluster used when hosting static sites."
  type        = string
  default     = null
}

variable "status" {
  description = "(optional) - This cluster's status."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "linode_object_storage_cluster" "this" {
  domain             = var.domain
  region             = var.region
  static_site_domain = var.static_site_domain
  status             = var.status
}
```

[top](#index)

### Outputs

```terraform
output "domain" {
  description = "returns a string"
  value       = data.linode_object_storage_cluster.this.domain
}

output "id" {
  description = "returns a string"
  value       = data.linode_object_storage_cluster.this.id
}

output "region" {
  description = "returns a string"
  value       = data.linode_object_storage_cluster.this.region
}

output "static_site_domain" {
  description = "returns a string"
  value       = data.linode_object_storage_cluster.this.static_site_domain
}

output "status" {
  description = "returns a string"
  value       = data.linode_object_storage_cluster.this.status
}

output "this" {
  value = linode_object_storage_cluster.this
}
```

[top](#index)