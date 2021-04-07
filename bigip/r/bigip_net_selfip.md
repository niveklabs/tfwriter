# bigip_net_selfip

[back](../bigip.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    bigip = ">= 1.8.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "bigip_net_selfip" {
  source = "./modules/bigip/r/bigip_net_selfip"

  # ip - (required) is a type of string
  ip = null
  # name - (required) is a type of string
  name = null
  # traffic_group - (optional) is a type of string
  traffic_group = null
  # vlan - (required) is a type of string
  vlan = null
}
```

[top](#index)

### Variables

```terraform
variable "ip" {
  description = "(required) - SelfIP IP address"
  type        = string
}

variable "name" {
  description = "(required) - Name of the SelfIP"
  type        = string
}

variable "traffic_group" {
  description = "(optional) - Name of the traffic group, defaults to traffic-group-local-only if not specified"
  type        = string
  default     = null
}

variable "vlan" {
  description = "(required) - Name of the vlan"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "bigip_net_selfip" "this" {
  # ip - (required) is a type of string
  ip = var.ip
  # name - (required) is a type of string
  name = var.name
  # traffic_group - (optional) is a type of string
  traffic_group = var.traffic_group
  # vlan - (required) is a type of string
  vlan = var.vlan
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = bigip_net_selfip.this.id
}

output "this" {
  value = bigip_net_selfip.this
}
```

[top](#index)