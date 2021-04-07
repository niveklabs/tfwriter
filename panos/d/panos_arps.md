# panos_arps

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
module "panos_arps" {
  source = "./modules/panos/d/panos_arps"

  # interface_name - (optional) is a type of string
  interface_name = null
  # interface_type - (optional) is a type of string
  interface_type = null
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
data "panos_arps" "this" {
  # interface_name - (optional) is a type of string
  interface_name = var.interface_name
  # interface_type - (optional) is a type of string
  interface_type = var.interface_type
  # subinterface_name - (optional) is a type of string
  subinterface_name = var.subinterface_name
  # template - (optional) is a type of string
  template = var.template
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.panos_arps.this.id
}

output "listing" {
  description = "returns a list of string"
  value       = data.panos_arps.this.listing
}

output "total" {
  description = "returns a number"
  value       = data.panos_arps.this.total
}

output "this" {
  value = panos_arps.this
}
```

[top](#index)