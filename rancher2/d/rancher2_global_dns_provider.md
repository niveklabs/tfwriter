# rancher2_global_dns_provider

[back](../rancher2.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    rancher2 = ">= 1.13.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "rancher2_global_dns_provider" {
  source = "./modules/rancher2/d/rancher2_global_dns_provider"

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
data "rancher2_global_dns_provider" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "alidns_config" {
  description = "returns a list of object"
  value       = data.rancher2_global_dns_provider.this.alidns_config
}

output "annotations" {
  description = "returns a map of string"
  value       = data.rancher2_global_dns_provider.this.annotations
}

output "cloudflare_config" {
  description = "returns a list of object"
  value       = data.rancher2_global_dns_provider.this.cloudflare_config
}

output "dns_provider" {
  description = "returns a string"
  value       = data.rancher2_global_dns_provider.this.dns_provider
}

output "id" {
  description = "returns a string"
  value       = data.rancher2_global_dns_provider.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = data.rancher2_global_dns_provider.this.labels
}

output "root_domain" {
  description = "returns a string"
  value       = data.rancher2_global_dns_provider.this.root_domain
}

output "route53_config" {
  description = "returns a list of object"
  value       = data.rancher2_global_dns_provider.this.route53_config
}

output "this" {
  value = rancher2_global_dns_provider.this
}
```

[top](#index)