# aviatrix_firenet

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
module "aviatrix_firenet" {
  source = "./modules/aviatrix/r/aviatrix_firenet"

  # egress_enabled - (optional) is a type of bool
  egress_enabled = null
  # hashing_algorithm - (optional) is a type of string
  hashing_algorithm = null
  # inspection_enabled - (optional) is a type of bool
  inspection_enabled = null
  # keep_alive_via_lan_interface_enabled - (optional) is a type of bool
  keep_alive_via_lan_interface_enabled = null
  # manage_firewall_instance_association - (optional) is a type of bool
  manage_firewall_instance_association = null
  # vpc_id - (required) is a type of string
  vpc_id = null

  firewall_instance_association = [{
    attached             = null
    egress_interface     = null
    firenet_gw_name      = null
    firewall_name        = null
    instance_id          = null
    lan_interface        = null
    management_interface = null
    vendor_type          = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "egress_enabled" {
  description = "(optional) - Enable/Disable egress through firewall."
  type        = bool
  default     = null
}

variable "hashing_algorithm" {
  description = "(optional) - Hashing algorithm to load balance traffic across the firewall."
  type        = string
  default     = null
}

variable "inspection_enabled" {
  description = "(optional) - Enable/Disable traffic inspection."
  type        = bool
  default     = null
}

variable "keep_alive_via_lan_interface_enabled" {
  description = "(optional) - Enable Keep Alive via Firewall LAN Interface."
  type        = bool
  default     = null
}

variable "manage_firewall_instance_association" {
  description = "(optional) - Enable this to manage firewall_instance_associations in-line. If this is false, associations must be managed via standalone aviatrix_firewall_instance_association resources. Type: boolean, Default: true, Valid values: true/false."
  type        = bool
  default     = null
}

variable "vpc_id" {
  description = "(required) - VPC ID."
  type        = string
}

variable "firewall_instance_association" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      attached             = bool
      egress_interface     = string
      firenet_gw_name      = string
      firewall_name        = string
      instance_id          = string
      lan_interface        = string
      management_interface = string
      vendor_type          = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_firenet" "this" {
  # egress_enabled - (optional) is a type of bool
  egress_enabled = var.egress_enabled
  # hashing_algorithm - (optional) is a type of string
  hashing_algorithm = var.hashing_algorithm
  # inspection_enabled - (optional) is a type of bool
  inspection_enabled = var.inspection_enabled
  # keep_alive_via_lan_interface_enabled - (optional) is a type of bool
  keep_alive_via_lan_interface_enabled = var.keep_alive_via_lan_interface_enabled
  # manage_firewall_instance_association - (optional) is a type of bool
  manage_firewall_instance_association = var.manage_firewall_instance_association
  # vpc_id - (required) is a type of string
  vpc_id = var.vpc_id

  dynamic "firewall_instance_association" {
    for_each = var.firewall_instance_association
    content {
      # attached - (optional) is a type of bool
      attached = firewall_instance_association.value["attached"]
      # egress_interface - (optional) is a type of string
      egress_interface = firewall_instance_association.value["egress_interface"]
      # firenet_gw_name - (required) is a type of string
      firenet_gw_name = firewall_instance_association.value["firenet_gw_name"]
      # firewall_name - (optional) is a type of string
      firewall_name = firewall_instance_association.value["firewall_name"]
      # instance_id - (required) is a type of string
      instance_id = firewall_instance_association.value["instance_id"]
      # lan_interface - (optional) is a type of string
      lan_interface = firewall_instance_association.value["lan_interface"]
      # management_interface - (optional) is a type of string
      management_interface = firewall_instance_association.value["management_interface"]
      # vendor_type - (optional) is a type of string
      vendor_type = firewall_instance_association.value["vendor_type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_firenet.this.id
}

output "this" {
  value = aviatrix_firenet.this
}
```

[top](#index)