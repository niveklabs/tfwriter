# google_netblock_ip_ranges

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_netblock_ip_ranges" {
  source = "./modules/google/d/google_netblock_ip_ranges"

  # range_type - (optional) is a type of string
  range_type = null
}
```

[top](#index)

### Variables

```terraform
variable "range_type" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "google_netblock_ip_ranges" "this" {
  range_type = var.range_type
}
```

[top](#index)

### Outputs

```terraform
output "cidr_blocks" {
  description = "returns a list of string"
  value       = data.google_netblock_ip_ranges.this.cidr_blocks
}

output "cidr_blocks_ipv4" {
  description = "returns a list of string"
  value       = data.google_netblock_ip_ranges.this.cidr_blocks_ipv4
}

output "cidr_blocks_ipv6" {
  description = "returns a list of string"
  value       = data.google_netblock_ip_ranges.this.cidr_blocks_ipv6
}

output "id" {
  description = "returns a string"
  value       = data.google_netblock_ip_ranges.this.id
}

output "this" {
  value = google_netblock_ip_ranges.this
}
```

[top](#index)