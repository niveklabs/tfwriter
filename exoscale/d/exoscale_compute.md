# exoscale_compute

[back](../exoscale.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    exoscale = ">= 0.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "exoscale_compute" {
  source = "./modules/exoscale/d/exoscale_compute"

  # hostname - (optional) is a type of string
  hostname = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "hostname" {
  description = "(optional) - Hostname of the Compute instance"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - Map of tags (key: value)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "exoscale_compute" "this" {
  hostname = var.hostname
  tags     = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "cpu" {
  description = "returns a number"
  value       = data.exoscale_compute.this.cpu
}

output "created" {
  description = "returns a string"
  value       = data.exoscale_compute.this.created
}

output "disk_size" {
  description = "returns a number"
  value       = data.exoscale_compute.this.disk_size
}

output "id" {
  description = "returns a string"
  value       = data.exoscale_compute.this.id
}

output "ip6_address" {
  description = "returns a string"
  value       = data.exoscale_compute.this.ip6_address
}

output "ip_address" {
  description = "returns a string"
  value       = data.exoscale_compute.this.ip_address
}

output "memory" {
  description = "returns a number"
  value       = data.exoscale_compute.this.memory
}

output "private_network_ip_addresses" {
  description = "returns a list of string"
  value       = data.exoscale_compute.this.private_network_ip_addresses
}

output "size" {
  description = "returns a string"
  value       = data.exoscale_compute.this.size
}

output "state" {
  description = "returns a string"
  value       = data.exoscale_compute.this.state
}

output "template" {
  description = "returns a string"
  value       = data.exoscale_compute.this.template
}

output "zone" {
  description = "returns a string"
  value       = data.exoscale_compute.this.zone
}

output "this" {
  value = exoscale_compute.this
}
```

[top](#index)