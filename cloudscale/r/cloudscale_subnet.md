# cloudscale_subnet

[back](../cloudscale.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    cloudscale = ">= 2.3.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "cloudscale_subnet" {
  source = "./modules/cloudscale/r/cloudscale_subnet"

  # cidr - (required) is a type of string
  cidr = null
  # dns_servers - (optional) is a type of list of string
  dns_servers = []
  # gateway_address - (optional) is a type of string
  gateway_address = null
  # network_uuid - (optional) is a type of string
  network_uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "cidr" {
  description = "(required)"
  type        = string
}

variable "dns_servers" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "gateway_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "network_uuid" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "cloudscale_subnet" "this" {
  # cidr - (required) is a type of string
  cidr = var.cidr
  # dns_servers - (optional) is a type of list of string
  dns_servers = var.dns_servers
  # gateway_address - (optional) is a type of string
  gateway_address = var.gateway_address
  # network_uuid - (optional) is a type of string
  network_uuid = var.network_uuid
}
```

[top](#index)

### Outputs

```terraform
output "dns_servers" {
  description = "returns a list of string"
  value       = cloudscale_subnet.this.dns_servers
}

output "gateway_address" {
  description = "returns a string"
  value       = cloudscale_subnet.this.gateway_address
}

output "href" {
  description = "returns a string"
  value       = cloudscale_subnet.this.href
}

output "id" {
  description = "returns a string"
  value       = cloudscale_subnet.this.id
}

output "network_href" {
  description = "returns a string"
  value       = cloudscale_subnet.this.network_href
}

output "network_name" {
  description = "returns a string"
  value       = cloudscale_subnet.this.network_name
}

output "this" {
  value = cloudscale_subnet.this
}
```

[top](#index)