# ecl_network_subnet_v2

[back](../ecl.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ecl = ">= 2.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ecl_network_subnet_v2" {
  source = "./modules/ecl/d/ecl_network_subnet_v2"

  # cidr - (optional) is a type of string
  cidr = null
  # description - (optional) is a type of string
  description = null
  # gateway_ip - (optional) is a type of string
  gateway_ip = null
  # name - (optional) is a type of string
  name = null
  # network_id - (optional) is a type of string
  network_id = null
  # region - (optional) is a type of string
  region = null
  # subnet_id - (optional) is a type of string
  subnet_id = null
}
```

[top](#index)

### Variables

```terraform
variable "cidr" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gateway_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "network_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subnet_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "ecl_network_subnet_v2" "this" {
  # cidr - (optional) is a type of string
  cidr = var.cidr
  # description - (optional) is a type of string
  description = var.description
  # gateway_ip - (optional) is a type of string
  gateway_ip = var.gateway_ip
  # name - (optional) is a type of string
  name = var.name
  # network_id - (optional) is a type of string
  network_id = var.network_id
  # region - (optional) is a type of string
  region = var.region
  # subnet_id - (optional) is a type of string
  subnet_id = var.subnet_id
}
```

[top](#index)

### Outputs

```terraform
output "allocation_pools" {
  description = "returns a list of object"
  value       = data.ecl_network_subnet_v2.this.allocation_pools
}

output "cidr" {
  description = "returns a string"
  value       = data.ecl_network_subnet_v2.this.cidr
}

output "description" {
  description = "returns a string"
  value       = data.ecl_network_subnet_v2.this.description
}

output "dns_nameservers" {
  description = "returns a list of string"
  value       = data.ecl_network_subnet_v2.this.dns_nameservers
}

output "enable_dhcp" {
  description = "returns a bool"
  value       = data.ecl_network_subnet_v2.this.enable_dhcp
}

output "gateway_ip" {
  description = "returns a string"
  value       = data.ecl_network_subnet_v2.this.gateway_ip
}

output "host_routes" {
  description = "returns a list of object"
  value       = data.ecl_network_subnet_v2.this.host_routes
}

output "id" {
  description = "returns a string"
  value       = data.ecl_network_subnet_v2.this.id
}

output "ip_version" {
  description = "returns a number"
  value       = data.ecl_network_subnet_v2.this.ip_version
}

output "ipv6_address_mode" {
  description = "returns a string"
  value       = data.ecl_network_subnet_v2.this.ipv6_address_mode
}

output "ipv6_ra_mode" {
  description = "returns a string"
  value       = data.ecl_network_subnet_v2.this.ipv6_ra_mode
}

output "name" {
  description = "returns a string"
  value       = data.ecl_network_subnet_v2.this.name
}

output "network_id" {
  description = "returns a string"
  value       = data.ecl_network_subnet_v2.this.network_id
}

output "ntp_servers" {
  description = "returns a list of string"
  value       = data.ecl_network_subnet_v2.this.ntp_servers
}

output "region" {
  description = "returns a string"
  value       = data.ecl_network_subnet_v2.this.region
}

output "status" {
  description = "returns a string"
  value       = data.ecl_network_subnet_v2.this.status
}

output "subnet_id" {
  description = "returns a string"
  value       = data.ecl_network_subnet_v2.this.subnet_id
}

output "tags" {
  description = "returns a map of string"
  value       = data.ecl_network_subnet_v2.this.tags
}

output "tenant_id" {
  description = "returns a string"
  value       = data.ecl_network_subnet_v2.this.tenant_id
}

output "this" {
  value = ecl_network_subnet_v2.this
}
```

[top](#index)