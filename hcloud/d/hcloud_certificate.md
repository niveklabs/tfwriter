# hcloud_certificate

[back](../hcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "hcloud_certificate" {
  source = "./modules/hcloud/d/hcloud_certificate"

  # name - (optional) is a type of string
  name = null
  # with_selector - (optional) is a type of string
  with_selector = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "with_selector" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "hcloud_certificate" "this" {
  name          = var.name
  with_selector = var.with_selector
}
```

[top](#index)

### Outputs

```terraform
output "certificate" {
  description = "returns a string"
  value       = data.hcloud_certificate.this.certificate
}

output "created" {
  description = "returns a string"
  value       = data.hcloud_certificate.this.created
}

output "domain_names" {
  description = "returns a list of string"
  value       = data.hcloud_certificate.this.domain_names
}

output "fingerprint" {
  description = "returns a string"
  value       = data.hcloud_certificate.this.fingerprint
}

output "id" {
  description = "returns a number"
  value       = data.hcloud_certificate.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = data.hcloud_certificate.this.labels
}

output "not_valid_after" {
  description = "returns a string"
  value       = data.hcloud_certificate.this.not_valid_after
}

output "not_valid_before" {
  description = "returns a string"
  value       = data.hcloud_certificate.this.not_valid_before
}

output "type" {
  description = "returns a string"
  value       = data.hcloud_certificate.this.type
}

output "this" {
  value = hcloud_certificate.this
}
```

[top](#index)