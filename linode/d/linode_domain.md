# linode_domain

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
module "linode_domain" {
  source = "./modules/linode/d/linode_domain"

  # domain - (optional) is a type of string
  domain = null
}
```

[top](#index)

### Variables

```terraform
variable "domain" {
  description = "(optional) - The domain this Domain represents. These must be unique in Linode's system; there cannot be two Domain records representing the same domain."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "linode_domain" "this" {
  domain = var.domain
}
```

[top](#index)

### Outputs

```terraform
output "axfr_ips" {
  description = "returns a set of string"
  value       = data.linode_domain.this.axfr_ips
}

output "description" {
  description = "returns a string"
  value       = data.linode_domain.this.description
}

output "expire_sec" {
  description = "returns a number"
  value       = data.linode_domain.this.expire_sec
}

output "group" {
  description = "returns a string"
  value       = data.linode_domain.this.group
}

output "id" {
  description = "returns a string"
  value       = data.linode_domain.this.id
}

output "master_ips" {
  description = "returns a set of string"
  value       = data.linode_domain.this.master_ips
}

output "refresh_sec" {
  description = "returns a number"
  value       = data.linode_domain.this.refresh_sec
}

output "retry_sec" {
  description = "returns a number"
  value       = data.linode_domain.this.retry_sec
}

output "soa_email" {
  description = "returns a string"
  value       = data.linode_domain.this.soa_email
}

output "status" {
  description = "returns a string"
  value       = data.linode_domain.this.status
}

output "tags" {
  description = "returns a set of string"
  value       = data.linode_domain.this.tags
}

output "ttl_sec" {
  description = "returns a number"
  value       = data.linode_domain.this.ttl_sec
}

output "type" {
  description = "returns a string"
  value       = data.linode_domain.this.type
}

output "this" {
  value = linode_domain.this
}
```

[top](#index)