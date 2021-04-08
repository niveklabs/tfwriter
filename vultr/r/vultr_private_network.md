# vultr_private_network

[back](../vultr.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vultr = ">= 2.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vultr_private_network" {
  source = "./modules/vultr/r/vultr_private_network"

  # description - (optional) is a type of string
  description = null
  # region - (required) is a type of string
  region = null
  # v4_subnet - (optional) is a type of string
  v4_subnet = null
  # v4_subnet_mask - (optional) is a type of number
  v4_subnet_mask = null
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

variable "region" {
  description = "(required)"
  type        = string
}

variable "v4_subnet" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "v4_subnet_mask" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vultr_private_network" "this" {
  # description - (optional) is a type of string
  description = var.description
  # region - (required) is a type of string
  region = var.region
  # v4_subnet - (optional) is a type of string
  v4_subnet = var.v4_subnet
  # v4_subnet_mask - (optional) is a type of number
  v4_subnet_mask = var.v4_subnet_mask
}
```

[top](#index)

### Outputs

```terraform
output "date_created" {
  description = "returns a string"
  value       = vultr_private_network.this.date_created
}

output "id" {
  description = "returns a string"
  value       = vultr_private_network.this.id
}

output "v4_subnet" {
  description = "returns a string"
  value       = vultr_private_network.this.v4_subnet
}

output "v4_subnet_mask" {
  description = "returns a number"
  value       = vultr_private_network.this.v4_subnet_mask
}

output "this" {
  value = vultr_private_network.this
}
```

[top](#index)