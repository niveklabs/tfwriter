# digitalocean_certificate

[back](../digitalocean.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    digitalocean = ">= 2.3.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "digitalocean_certificate" {
  source = "./modules/digitalocean/r/digitalocean_certificate"

  # certificate_chain - (optional) is a type of string
  certificate_chain = null
  # domains - (optional) is a type of set of string
  domains = []
  # leaf_certificate - (optional) is a type of string
  leaf_certificate = null
  # name - (required) is a type of string
  name = null
  # private_key - (optional) is a type of string
  private_key = null
  # type - (optional) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "certificate_chain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "domains" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "leaf_certificate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "private_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "digitalocean_certificate" "this" {
  certificate_chain = var.certificate_chain
  domains           = var.domains
  leaf_certificate  = var.leaf_certificate
  name              = var.name
  private_key       = var.private_key
  type              = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = digitalocean_certificate.this.id
}

output "not_after" {
  description = "returns a string"
  value       = digitalocean_certificate.this.not_after
}

output "sha1_fingerprint" {
  description = "returns a string"
  value       = digitalocean_certificate.this.sha1_fingerprint
}

output "state" {
  description = "returns a string"
  value       = digitalocean_certificate.this.state
}

output "uuid" {
  description = "returns a string"
  value       = digitalocean_certificate.this.uuid
}

output "this" {
  value = digitalocean_certificate.this
}
```

[top](#index)