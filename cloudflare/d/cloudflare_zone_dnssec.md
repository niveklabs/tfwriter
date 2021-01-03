# cloudflare_zone_dnssec

[back](../cloudflare.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    cloudflare = ">= 2.15.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "cloudflare_zone_dnssec" {
  source = "./modules/cloudflare/d/cloudflare_zone_dnssec"

  # zone_id - (required) is a type of string
  zone_id = null
}
```

[top](#index)

### Variables

```terraform
variable "zone_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "cloudflare_zone_dnssec" "this" {
  zone_id = var.zone_id
}
```

[top](#index)

### Outputs

```terraform
output "algorithm" {
  description = "returns a string"
  value       = data.cloudflare_zone_dnssec.this.algorithm
}

output "digest" {
  description = "returns a string"
  value       = data.cloudflare_zone_dnssec.this.digest
}

output "digest_algorithm" {
  description = "returns a string"
  value       = data.cloudflare_zone_dnssec.this.digest_algorithm
}

output "digest_type" {
  description = "returns a string"
  value       = data.cloudflare_zone_dnssec.this.digest_type
}

output "ds" {
  description = "returns a string"
  value       = data.cloudflare_zone_dnssec.this.ds
}

output "flags" {
  description = "returns a number"
  value       = data.cloudflare_zone_dnssec.this.flags
}

output "id" {
  description = "returns a string"
  value       = data.cloudflare_zone_dnssec.this.id
}

output "key_tag" {
  description = "returns a number"
  value       = data.cloudflare_zone_dnssec.this.key_tag
}

output "key_type" {
  description = "returns a string"
  value       = data.cloudflare_zone_dnssec.this.key_type
}

output "public_key" {
  description = "returns a string"
  value       = data.cloudflare_zone_dnssec.this.public_key
}

output "status" {
  description = "returns a string"
  value       = data.cloudflare_zone_dnssec.this.status
}

output "this" {
  value = cloudflare_zone_dnssec.this
}
```

[top](#index)