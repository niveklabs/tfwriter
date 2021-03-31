# opc_compute_ip_network

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
module "opc_compute_ip_network" {
  source = "./modules/opc/r/opc_compute_ip_network"

  # description - (optional) is a type of string
  description = null
  # ip_address_prefix - (required) is a type of string
  ip_address_prefix = null
  # ip_network_exchange - (optional) is a type of string
  ip_network_exchange = null
  # name - (required) is a type of string
  name = null
  # public_napt_enabled - (optional) is a type of bool
  public_napt_enabled = null
  # tags - (optional) is a type of list of string
  tags = []
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

variable "ip_address_prefix" {
  description = "(required)"
  type        = string
}

variable "ip_network_exchange" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "public_napt_enabled" {
  description = "(optional)"
  type        = bool
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
resource "opc_compute_ip_network" "this" {
  description         = var.description
  ip_address_prefix   = var.ip_address_prefix
  ip_network_exchange = var.ip_network_exchange
  name                = var.name
  public_napt_enabled = var.public_napt_enabled
  tags                = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = opc_compute_ip_network.this.id
}

output "uri" {
  description = "returns a string"
  value       = opc_compute_ip_network.this.uri
}

output "this" {
  value = opc_compute_ip_network.this
}
```

[top](#index)