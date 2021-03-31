# opc_compute_security_rule

[back](../opc.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    opc = ">= 1.4.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "opc_compute_security_rule" {
  source = "./modules/opc/r/opc_compute_security_rule"

  # acl - (optional) is a type of string
  acl = null
  # description - (optional) is a type of string
  description = null
  # dst_ip_address_prefixes - (optional) is a type of list of string
  dst_ip_address_prefixes = []
  # dst_vnic_set - (optional) is a type of string
  dst_vnic_set = null
  # enabled - (optional) is a type of bool
  enabled = null
  # flow_direction - (required) is a type of string
  flow_direction = null
  # name - (required) is a type of string
  name = null
  # security_protocols - (optional) is a type of list of string
  security_protocols = []
  # src_ip_address_prefixes - (optional) is a type of list of string
  src_ip_address_prefixes = []
  # src_vnic_set - (optional) is a type of string
  src_vnic_set = null
  # tags - (optional) is a type of list of string
  tags = []
}
```

[top](#index)

### Variables

```terraform
variable "acl" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dst_ip_address_prefixes" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "dst_vnic_set" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "flow_direction" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "security_protocols" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "src_ip_address_prefixes" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "src_vnic_set" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = list(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "opc_compute_security_rule" "this" {
  acl                     = var.acl
  description             = var.description
  dst_ip_address_prefixes = var.dst_ip_address_prefixes
  dst_vnic_set            = var.dst_vnic_set
  enabled                 = var.enabled
  flow_direction          = var.flow_direction
  name                    = var.name
  security_protocols      = var.security_protocols
  src_ip_address_prefixes = var.src_ip_address_prefixes
  src_vnic_set            = var.src_vnic_set
  tags                    = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = opc_compute_security_rule.this.id
}

output "uri" {
  description = "returns a string"
  value       = opc_compute_security_rule.this.uri
}

output "this" {
  value = opc_compute_security_rule.this
}
```

[top](#index)