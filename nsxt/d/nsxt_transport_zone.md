# nsxt_transport_zone

[back](../nsxt.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nsxt = ">= 3.1.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nsxt_transport_zone" {
  source = "./modules/nsxt/d/nsxt_transport_zone"

  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # host_switch_name - (optional) is a type of string
  host_switch_name = null
  # transport_type - (optional) is a type of string
  transport_type = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description of this resource"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional) - The display name of this resource"
  type        = string
  default     = null
}

variable "host_switch_name" {
  description = "(optional) - Name of the host switch on all transport nodes in this transport zone that will be used to run NSX network traffic"
  type        = string
  default     = null
}

variable "transport_type" {
  description = "(optional) - The transport type of this transport zone (OVERLAY or VLAN)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "nsxt_transport_zone" "this" {
  # description - (optional) is a type of string
  description = var.description
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # host_switch_name - (optional) is a type of string
  host_switch_name = var.host_switch_name
  # transport_type - (optional) is a type of string
  transport_type = var.transport_type
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.nsxt_transport_zone.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.nsxt_transport_zone.this.display_name
}

output "host_switch_name" {
  description = "returns a string"
  value       = data.nsxt_transport_zone.this.host_switch_name
}

output "id" {
  description = "returns a string"
  value       = data.nsxt_transport_zone.this.id
}

output "transport_type" {
  description = "returns a string"
  value       = data.nsxt_transport_zone.this.transport_type
}

output "this" {
  value = nsxt_transport_zone.this
}
```

[top](#index)