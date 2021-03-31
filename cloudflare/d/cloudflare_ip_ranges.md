# cloudflare_ip_ranges

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
    cloudflare = ">= 2.19.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "cloudflare_ip_ranges" {
  source = "./modules/cloudflare/d/cloudflare_ip_ranges"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "cloudflare_ip_ranges" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "china_ipv4_cidr_blocks" {
  description = "returns a list of string"
  value       = data.cloudflare_ip_ranges.this.china_ipv4_cidr_blocks
}

output "china_ipv6_cidr_blocks" {
  description = "returns a list of string"
  value       = data.cloudflare_ip_ranges.this.china_ipv6_cidr_blocks
}

output "cidr_blocks" {
  description = "returns a list of string"
  value       = data.cloudflare_ip_ranges.this.cidr_blocks
}

output "id" {
  description = "returns a string"
  value       = data.cloudflare_ip_ranges.this.id
}

output "ipv4_cidr_blocks" {
  description = "returns a list of string"
  value       = data.cloudflare_ip_ranges.this.ipv4_cidr_blocks
}

output "ipv6_cidr_blocks" {
  description = "returns a list of string"
  value       = data.cloudflare_ip_ranges.this.ipv6_cidr_blocks
}

output "this" {
  value = cloudflare_ip_ranges.this
}
```

[top](#index)