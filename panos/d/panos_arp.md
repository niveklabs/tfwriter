# panos_arp

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    panos = ">= 1.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_arp" {
  source = "./modules/panos/d/panos_arp"

  # interface_name - (optional) is a type of string
  interface_name = null
  # interface_type - (optional) is a type of string
  interface_type = null
  # ip - (required) is a type of string
  ip = null
  # subinterface_name - (optional) is a type of string
  subinterface_name = null
  # template - (optional) is a type of string
  template = null
}
```

[top](#index)

### Variables

```terraform
variable "interface_name" {
  description = "(optional) - The interface name; leave this empty for VLAN interfaces"
  type        = string
  default     = null
}

variable "interface_type" {
  description = "(optional) - The interface type"
  type        = string
  default     = null
}

variable "ip" {
  description = "(required) - The IP address"
  type        = string
}

variable "subinterface_name" {
  description = "(optional) - The subinterface name"
  type        = string
  default     = null
}

variable "template" {
  description = "(optional) - (If Panorama) The template where the interface is"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "panos_arp" "this" {
  interface_name    = var.interface_name
  interface_type    = var.interface_type
  ip                = var.ip
  subinterface_name = var.subinterface_name
  template          = var.template
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.panos_arp.this.id
}

output "interface" {
  description = "returns a string"
  value       = data.panos_arp.this.interface
}

output "mac_address" {
  description = "returns a string"
  value       = data.panos_arp.this.mac_address
}

output "this" {
  value = panos_arp.this
}
```

[top](#index)