# packet_ip_block_ranges

[back](../packet.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    packet = ">= 3.2.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "packet_ip_block_ranges" {
  source = "./modules/packet/d/packet_ip_block_ranges"

  # facility - (optional) is a type of string
  facility = null
  # project_id - (required) is a type of string
  project_id = null
}
```

[top](#index)

### Variables

```terraform
variable "facility" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "project_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "packet_ip_block_ranges" "this" {
  facility   = var.facility
  project_id = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "global_ipv4" {
  description = "returns a list of string"
  value       = data.packet_ip_block_ranges.this.global_ipv4
}

output "id" {
  description = "returns a string"
  value       = data.packet_ip_block_ranges.this.id
}

output "ipv6" {
  description = "returns a list of string"
  value       = data.packet_ip_block_ranges.this.ipv6
}

output "private_ipv4" {
  description = "returns a list of string"
  value       = data.packet_ip_block_ranges.this.private_ipv4
}

output "public_ipv4" {
  description = "returns a list of string"
  value       = data.packet_ip_block_ranges.this.public_ipv4
}

output "this" {
  value = packet_ip_block_ranges.this
}
```

[top](#index)