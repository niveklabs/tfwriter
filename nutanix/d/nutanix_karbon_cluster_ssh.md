# nutanix_karbon_cluster_ssh

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
module "nutanix_karbon_cluster_ssh" {
  source = "./modules/nutanix/d/nutanix_karbon_cluster_ssh"

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
data "nutanix_karbon_cluster_ssh" "this" {
  karbon_cluster_id   = var.karbon_cluster_id
  karbon_cluster_name = var.karbon_cluster_name
}
```

[top](#index)

### Outputs

```terraform
output "certificate" {
  description = "returns a string"
  value       = data.nutanix_karbon_cluster_ssh.this.certificate
}

output "expiry_time" {
  description = "returns a string"
  value       = data.nutanix_karbon_cluster_ssh.this.expiry_time
}

output "id" {
  description = "returns a string"
  value       = data.nutanix_karbon_cluster_ssh.this.id
}

output "private_key" {
  description = "returns a string"
  value       = data.nutanix_karbon_cluster_ssh.this.private_key
}

output "username" {
  description = "returns a string"
  value       = data.nutanix_karbon_cluster_ssh.this.username
}

output "this" {
  value = nutanix_karbon_cluster_ssh.this
}
```

[top](#index)