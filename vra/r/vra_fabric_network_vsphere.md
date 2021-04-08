# vra_fabric_network_vsphere

[back](../vra.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vra = ">= 0.3.5"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vra_fabric_network_vsphere" {
  source = "./modules/vra/r/vra_fabric_network_vsphere"

  # cidr - (optional) is a type of string
  cidr = null
  # default_gateway - (optional) is a type of string
  default_gateway = null
  # default_ipv6_gateway - (optional) is a type of string
  default_ipv6_gateway = null
  # dns_search_domains - (optional) is a type of list of string
  dns_search_domains = []
  # dns_server_addresses - (optional) is a type of list of string
  dns_server_addresses = []
  # domain - (optional) is a type of string
  domain = null
  # ipv6_cidr - (optional) is a type of string
  ipv6_cidr = null
  # is_default - (optional) is a type of bool
  is_default = null
  # is_public - (optional) is a type of bool
  is_public = null

  tags = [{
    key   = null
    value = null
  }]
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

variable "default_gateway" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_ipv6_gateway" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dns_search_domains" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "dns_server_addresses" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "domain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv6_cidr" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "is_default" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "is_public" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "tags" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      key   = string
      value = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "vra_fabric_network_vsphere" "this" {
  # cidr - (optional) is a type of string
  cidr = var.cidr
  # default_gateway - (optional) is a type of string
  default_gateway = var.default_gateway
  # default_ipv6_gateway - (optional) is a type of string
  default_ipv6_gateway = var.default_ipv6_gateway
  # dns_search_domains - (optional) is a type of list of string
  dns_search_domains = var.dns_search_domains
  # dns_server_addresses - (optional) is a type of list of string
  dns_server_addresses = var.dns_server_addresses
  # domain - (optional) is a type of string
  domain = var.domain
  # ipv6_cidr - (optional) is a type of string
  ipv6_cidr = var.ipv6_cidr
  # is_default - (optional) is a type of bool
  is_default = var.is_default
  # is_public - (optional) is a type of bool
  is_public = var.is_public

  dynamic "tags" {
    for_each = var.tags
    content {
      # key - (required) is a type of string
      key = tags.value["key"]
      # value - (required) is a type of string
      value = tags.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cidr" {
  description = "returns a string"
  value       = vra_fabric_network_vsphere.this.cidr
}

output "cloud_account_ids" {
  description = "returns a list of string"
  value       = vra_fabric_network_vsphere.this.cloud_account_ids
}

output "created_at" {
  description = "returns a string"
  value       = vra_fabric_network_vsphere.this.created_at
}

output "default_gateway" {
  description = "returns a string"
  value       = vra_fabric_network_vsphere.this.default_gateway
}

output "default_ipv6_gateway" {
  description = "returns a string"
  value       = vra_fabric_network_vsphere.this.default_ipv6_gateway
}

output "dns_search_domains" {
  description = "returns a list of string"
  value       = vra_fabric_network_vsphere.this.dns_search_domains
}

output "dns_server_addresses" {
  description = "returns a list of string"
  value       = vra_fabric_network_vsphere.this.dns_server_addresses
}

output "external_id" {
  description = "returns a string"
  value       = vra_fabric_network_vsphere.this.external_id
}

output "external_region_id" {
  description = "returns a string"
  value       = vra_fabric_network_vsphere.this.external_region_id
}

output "id" {
  description = "returns a string"
  value       = vra_fabric_network_vsphere.this.id
}

output "links" {
  description = "returns a set of object"
  value       = vra_fabric_network_vsphere.this.links
}

output "name" {
  description = "returns a string"
  value       = vra_fabric_network_vsphere.this.name
}

output "org_id" {
  description = "returns a string"
  value       = vra_fabric_network_vsphere.this.org_id
}

output "organization_id" {
  description = "returns a string"
  value       = vra_fabric_network_vsphere.this.organization_id
}

output "updated_at" {
  description = "returns a string"
  value       = vra_fabric_network_vsphere.this.updated_at
}

output "this" {
  value = vra_fabric_network_vsphere.this
}
```

[top](#index)