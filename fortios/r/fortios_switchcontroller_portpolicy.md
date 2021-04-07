# fortios_switchcontroller_portpolicy

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_switchcontroller_portpolicy" {
  source = "./modules/fortios/r/fortios_switchcontroller_portpolicy"

  # bounce_port_link - (optional) is a type of string
  bounce_port_link = null
  # description - (optional) is a type of string
  description = null
  # fortilink - (optional) is a type of string
  fortilink = null
  # lldp_profile - (optional) is a type of string
  lldp_profile = null
  # n802_1x - (optional) is a type of string
  n802_1x = null
  # name - (optional) is a type of string
  name = null
  # qos_policy - (optional) is a type of string
  qos_policy = null
  # vlan_policy - (optional) is a type of string
  vlan_policy = null
}
```

[top](#index)

### Variables

```terraform
variable "bounce_port_link" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fortilink" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "lldp_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "n802_1x" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "qos_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vlan_policy" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_switchcontroller_portpolicy" "this" {
  # bounce_port_link - (optional) is a type of string
  bounce_port_link = var.bounce_port_link
  # description - (optional) is a type of string
  description = var.description
  # fortilink - (optional) is a type of string
  fortilink = var.fortilink
  # lldp_profile - (optional) is a type of string
  lldp_profile = var.lldp_profile
  # n802_1x - (optional) is a type of string
  n802_1x = var.n802_1x
  # name - (optional) is a type of string
  name = var.name
  # qos_policy - (optional) is a type of string
  qos_policy = var.qos_policy
  # vlan_policy - (optional) is a type of string
  vlan_policy = var.vlan_policy
}
```

[top](#index)

### Outputs

```terraform
output "bounce_port_link" {
  description = "returns a string"
  value       = fortios_switchcontroller_portpolicy.this.bounce_port_link
}

output "description" {
  description = "returns a string"
  value       = fortios_switchcontroller_portpolicy.this.description
}

output "fortilink" {
  description = "returns a string"
  value       = fortios_switchcontroller_portpolicy.this.fortilink
}

output "id" {
  description = "returns a string"
  value       = fortios_switchcontroller_portpolicy.this.id
}

output "lldp_profile" {
  description = "returns a string"
  value       = fortios_switchcontroller_portpolicy.this.lldp_profile
}

output "n802_1x" {
  description = "returns a string"
  value       = fortios_switchcontroller_portpolicy.this.n802_1x
}

output "name" {
  description = "returns a string"
  value       = fortios_switchcontroller_portpolicy.this.name
}

output "qos_policy" {
  description = "returns a string"
  value       = fortios_switchcontroller_portpolicy.this.qos_policy
}

output "vlan_policy" {
  description = "returns a string"
  value       = fortios_switchcontroller_portpolicy.this.vlan_policy
}

output "this" {
  value = fortios_switchcontroller_portpolicy.this
}
```

[top](#index)