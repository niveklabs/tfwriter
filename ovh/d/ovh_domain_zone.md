# ovh_domain_zone

[back](../ovh.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ovh = ">= 0.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ovh_domain_zone" {
  source = "./modules/ovh/d/ovh_domain_zone"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "ovh_domain_zone" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "dnssec_supported" {
  description = "returns a bool"
  value       = data.ovh_domain_zone.this.dnssec_supported
}

output "has_dns_anycast" {
  description = "returns a bool"
  value       = data.ovh_domain_zone.this.has_dns_anycast
}

output "id" {
  description = "returns a string"
  value       = data.ovh_domain_zone.this.id
}

output "last_update" {
  description = "returns a string"
  value       = data.ovh_domain_zone.this.last_update
}

output "name_servers" {
  description = "returns a set of string"
  value       = data.ovh_domain_zone.this.name_servers
}

output "this" {
  value = ovh_domain_zone.this
}
```

[top](#index)