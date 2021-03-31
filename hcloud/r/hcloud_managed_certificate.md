# hcloud_managed_certificate

[back](../hcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    hcloud = ">= 1.26.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "hcloud_managed_certificate" {
  source = "./modules/hcloud/r/hcloud_managed_certificate"

  # domain_names - (required) is a type of set of string
  domain_names = []
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "domain_names" {
  description = "(required)"
  type        = set(string)
}

variable "labels" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "hcloud_managed_certificate" "this" {
  domain_names = var.domain_names
  labels       = var.labels
  name         = var.name
}
```

[top](#index)

### Outputs

```terraform
output "certificate" {
  description = "returns a string"
  value       = hcloud_managed_certificate.this.certificate
}

output "created" {
  description = "returns a string"
  value       = hcloud_managed_certificate.this.created
}

output "fingerprint" {
  description = "returns a string"
  value       = hcloud_managed_certificate.this.fingerprint
}

output "id" {
  description = "returns a string"
  value       = hcloud_managed_certificate.this.id
}

output "not_valid_after" {
  description = "returns a string"
  value       = hcloud_managed_certificate.this.not_valid_after
}

output "not_valid_before" {
  description = "returns a string"
  value       = hcloud_managed_certificate.this.not_valid_before
}

output "type" {
  description = "returns a string"
  value       = hcloud_managed_certificate.this.type
}

output "this" {
  value = hcloud_managed_certificate.this
}
```

[top](#index)