# fastly_ip_ranges

[back](../fastly.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fastly = ">= 0.28.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fastly_ip_ranges" {
  source = "./modules/fastly/d/fastly_ip_ranges"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "fastly_ip_ranges" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "cidr_blocks" {
  description = "returns a list of string"
  value       = data.fastly_ip_ranges.this.cidr_blocks
}

output "id" {
  description = "returns a string"
  value       = data.fastly_ip_ranges.this.id
}

output "ipv6_cidr_blocks" {
  description = "returns a list of string"
  value       = data.fastly_ip_ranges.this.ipv6_cidr_blocks
}

output "this" {
  value = fastly_ip_ranges.this
}
```

[top](#index)