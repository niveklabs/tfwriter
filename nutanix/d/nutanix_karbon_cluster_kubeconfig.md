# nutanix_karbon_cluster_kubeconfig

[back](../nutanix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nutanix = ">= 1.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nutanix_karbon_cluster_kubeconfig" {
  source = "./modules/nutanix/d/nutanix_karbon_cluster_kubeconfig"

  # karbon_cluster_id - (optional) is a type of string
  karbon_cluster_id = null
  # karbon_cluster_name - (optional) is a type of string
  karbon_cluster_name = null
}
```

[top](#index)

### Variables

```terraform
variable "karbon_cluster_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "karbon_cluster_name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "nutanix_karbon_cluster_kubeconfig" "this" {
  karbon_cluster_id   = var.karbon_cluster_id
  karbon_cluster_name = var.karbon_cluster_name
}
```

[top](#index)

### Outputs

```terraform
output "access_token" {
  description = "returns a string"
  value       = data.nutanix_karbon_cluster_kubeconfig.this.access_token
  sensitive   = true
}

output "cluster_ca_certificate" {
  description = "returns a string"
  value       = data.nutanix_karbon_cluster_kubeconfig.this.cluster_ca_certificate
}

output "cluster_url" {
  description = "returns a string"
  value       = data.nutanix_karbon_cluster_kubeconfig.this.cluster_url
}

output "id" {
  description = "returns a string"
  value       = data.nutanix_karbon_cluster_kubeconfig.this.id
}

output "name" {
  description = "returns a string"
  value       = data.nutanix_karbon_cluster_kubeconfig.this.name
}

output "this" {
  value = nutanix_karbon_cluster_kubeconfig.this
}
```

[top](#index)