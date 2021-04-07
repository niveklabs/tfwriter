# aviatrix_firewall_instance_association

[back](../aviatrix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aviatrix = ">= 2.18.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aviatrix_firewall_instance_association" {
  source = "./modules/aviatrix/r/aviatrix_firewall_instance_association"

  # attached - (optional) is a type of bool
  attached = null
  # egress_interface - (optional) is a type of string
  egress_interface = null
  # firenet_gw_name - (optional) is a type of string
  firenet_gw_name = null
  # firewall_name - (optional) is a type of string
  firewall_name = null
  # instance_id - (required) is a type of string
  instance_id = null
  # lan_interface - (optional) is a type of string
  lan_interface = null
  # management_interface - (optional) is a type of string
  management_interface = null
  # vendor_type - (optional) is a type of string
  vendor_type = null
  # vpc_id - (required) is a type of string
  vpc_id = null
}
```

[top](#index)

### Variables

```terraform
variable "attached" {
  description = "(optional) - Switch to attach/detach firewall instance to/from fireNet."
  type        = bool
  default     = null
}

variable "egress_interface" {
  description = "(optional) - Egress interface ID, required if it is a firewall instance."
  type        = string
  default     = null
}

variable "firenet_gw_name" {
  description = "(optional) - Name of the gateway to launch the firewall instance."
  type        = string
  default     = null
}

variable "firewall_name" {
  description = "(optional) - Firewall instance name, or FQDN Gateway's gw_name, required if it is a AWS or AZURE firewall instance. Not allowed for GCP"
  type        = string
  default     = null
}

variable "instance_id" {
  description = "(required) - ID of Firewall instance, or FQDN Gateway's gw_name."
  type        = string
}

variable "lan_interface" {
  description = "(optional) - Lan interface ID, required if it is a firewall instance."
  type        = string
  default     = null
}

variable "management_interface" {
  description = "(optional) - Management interface ID, required if it is a firewall instance."
  type        = string
  default     = null
}

variable "vendor_type" {
  description = "(optional) - Indication it is a firewall instance or FQDN gateway to be associated to fireNet. Valid values: 'Generic', 'fqdn_gateway'. Value 'fqdn_gateway' is required for FQDN gateway."
  type        = string
  default     = null
}

variable "vpc_id" {
  description = "(required) - VPC ID."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_firewall_instance_association" "this" {
  # attached - (optional) is a type of bool
  attached = var.attached
  # egress_interface - (optional) is a type of string
  egress_interface = var.egress_interface
  # firenet_gw_name - (optional) is a type of string
  firenet_gw_name = var.firenet_gw_name
  # firewall_name - (optional) is a type of string
  firewall_name = var.firewall_name
  # instance_id - (required) is a type of string
  instance_id = var.instance_id
  # lan_interface - (optional) is a type of string
  lan_interface = var.lan_interface
  # management_interface - (optional) is a type of string
  management_interface = var.management_interface
  # vendor_type - (optional) is a type of string
  vendor_type = var.vendor_type
  # vpc_id - (required) is a type of string
  vpc_id = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_firewall_instance_association.this.id
}

output "this" {
  value = aviatrix_firewall_instance_association.this
}
```

[top](#index)