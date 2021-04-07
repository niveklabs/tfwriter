# digitalocean_certificate

[back](../digitalocean.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    digitalocean = ">= 2.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "digitalocean_certificate" {
  source = "./modules/digitalocean/d/digitalocean_certificate"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - name of the certificate"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "digitalocean_certificate" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "domains" {
  description = "returns a set of string"
  value       = data.digitalocean_certificate.this.domains
}

output "id" {
  description = "returns a string"
  value       = data.digitalocean_certificate.this.id
}

output "not_after" {
  description = "returns a string"
  value       = data.digitalocean_certificate.this.not_after
}

output "sha1_fingerprint" {
  description = "returns a string"
  value       = data.digitalocean_certificate.this.sha1_fingerprint
}

output "state" {
  description = "returns a string"
  value       = data.digitalocean_certificate.this.state
}

output "type" {
  description = "returns a string"
  value       = data.digitalocean_certificate.this.type
}

output "uuid" {
  description = "returns a string"
  value       = data.digitalocean_certificate.this.uuid
}

output "this" {
  value = digitalocean_certificate.this
}
```

[top](#index)