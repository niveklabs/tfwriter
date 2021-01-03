# oci_core_subnet

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_core_subnet" {
  source = "./modules/oci/r/oci_core_subnet"

  # availability_domain - (optional) is a type of string
  availability_domain = null
  # cidr_block - (required) is a type of string
  cidr_block = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # dhcp_options_id - (optional) is a type of string
  dhcp_options_id = null
  # display_name - (optional) is a type of string
  display_name = null
  # dns_label - (optional) is a type of string
  dns_label = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # ipv6cidr_block - (optional) is a type of string
  ipv6cidr_block = null
  # prohibit_public_ip_on_vnic - (optional) is a type of bool
  prohibit_public_ip_on_vnic = null
  # route_table_id - (optional) is a type of string
  route_table_id = null
  # security_list_ids - (optional) is a type of set of string
  security_list_ids = []
  # vcn_id - (required) is a type of string
  vcn_id = null

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "availability_domain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cidr_block" {
  description = "(required)"
  type        = string
}

variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "dhcp_options_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dns_label" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "ipv6cidr_block" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "prohibit_public_ip_on_vnic" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "route_table_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_list_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "vcn_id" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "oci_core_subnet" "this" {
  availability_domain        = var.availability_domain
  cidr_block                 = var.cidr_block
  compartment_id             = var.compartment_id
  defined_tags               = var.defined_tags
  dhcp_options_id            = var.dhcp_options_id
  display_name               = var.display_name
  dns_label                  = var.dns_label
  freeform_tags              = var.freeform_tags
  ipv6cidr_block             = var.ipv6cidr_block
  prohibit_public_ip_on_vnic = var.prohibit_public_ip_on_vnic
  route_table_id             = var.route_table_id
  security_list_ids          = var.security_list_ids
  vcn_id                     = var.vcn_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "availability_domain" {
  description = "returns a string"
  value       = oci_core_subnet.this.availability_domain
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_core_subnet.this.defined_tags
}

output "dhcp_options_id" {
  description = "returns a string"
  value       = oci_core_subnet.this.dhcp_options_id
}

output "display_name" {
  description = "returns a string"
  value       = oci_core_subnet.this.display_name
}

output "dns_label" {
  description = "returns a string"
  value       = oci_core_subnet.this.dns_label
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_core_subnet.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_core_subnet.this.id
}

output "ipv6cidr_block" {
  description = "returns a string"
  value       = oci_core_subnet.this.ipv6cidr_block
}

output "ipv6public_cidr_block" {
  description = "returns a string"
  value       = oci_core_subnet.this.ipv6public_cidr_block
}

output "ipv6virtual_router_ip" {
  description = "returns a string"
  value       = oci_core_subnet.this.ipv6virtual_router_ip
}

output "prohibit_public_ip_on_vnic" {
  description = "returns a bool"
  value       = oci_core_subnet.this.prohibit_public_ip_on_vnic
}

output "route_table_id" {
  description = "returns a string"
  value       = oci_core_subnet.this.route_table_id
}

output "security_list_ids" {
  description = "returns a set of string"
  value       = oci_core_subnet.this.security_list_ids
}

output "state" {
  description = "returns a string"
  value       = oci_core_subnet.this.state
}

output "subnet_domain_name" {
  description = "returns a string"
  value       = oci_core_subnet.this.subnet_domain_name
}

output "time_created" {
  description = "returns a string"
  value       = oci_core_subnet.this.time_created
}

output "virtual_router_ip" {
  description = "returns a string"
  value       = oci_core_subnet.this.virtual_router_ip
}

output "virtual_router_mac" {
  description = "returns a string"
  value       = oci_core_subnet.this.virtual_router_mac
}

output "this" {
  value = oci_core_subnet.this
}
```

[top](#index)