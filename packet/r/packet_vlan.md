# packet_vlan

[back](../packet.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    packet = ">= 3.2.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "packet_vlan" {
  source = "./modules/packet/r/packet_vlan"

  # description - (optional) is a type of string
  description = null
  # facility - (required) is a type of string
  facility = null
  # project_id - (required) is a type of string
  project_id = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "facility" {
  description = "(required)"
  type        = string
}

variable "project_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "packet_vlan" "this" {
  description = var.description
  facility    = var.facility
  project_id  = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = packet_vlan.this.id
}

output "vxlan" {
  description = "returns a number"
  value       = packet_vlan.this.vxlan
}

output "this" {
  value = packet_vlan.this
}
```

[top](#index)