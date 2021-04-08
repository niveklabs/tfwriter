# vultr_object_storage

[back](../vultr.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vultr = ">= 2.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vultr_object_storage" {
  source = "./modules/vultr/r/vultr_object_storage"

  # cluster_id - (required) is a type of number
  cluster_id = null
  # label - (optional) is a type of string
  label = null
}
```

[top](#index)

### Variables

```terraform
variable "cluster_id" {
  description = "(required)"
  type        = number
}

variable "label" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vultr_object_storage" "this" {
  # cluster_id - (required) is a type of number
  cluster_id = var.cluster_id
  # label - (optional) is a type of string
  label = var.label
}
```

[top](#index)

### Outputs

```terraform
output "date_created" {
  description = "returns a string"
  value       = vultr_object_storage.this.date_created
}

output "id" {
  description = "returns a string"
  value       = vultr_object_storage.this.id
}

output "location" {
  description = "returns a string"
  value       = vultr_object_storage.this.location
}

output "region" {
  description = "returns a string"
  value       = vultr_object_storage.this.region
}

output "s3_access_key" {
  description = "returns a string"
  value       = vultr_object_storage.this.s3_access_key
  sensitive   = true
}

output "s3_hostname" {
  description = "returns a string"
  value       = vultr_object_storage.this.s3_hostname
}

output "s3_secret_key" {
  description = "returns a string"
  value       = vultr_object_storage.this.s3_secret_key
  sensitive   = true
}

output "status" {
  description = "returns a string"
  value       = vultr_object_storage.this.status
}

output "this" {
  value = vultr_object_storage.this
}
```

[top](#index)