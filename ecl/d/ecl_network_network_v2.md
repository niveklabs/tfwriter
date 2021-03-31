# ecl_network_network_v2

[back](../ecl.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ecl = ">= 1.13.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ecl_network_network_v2" {
  source = "./modules/ecl/d/ecl_network_network_v2"

  # description - (optional) is a type of string
  description = null
  # matching_subnet_cidr - (optional) is a type of string
  matching_subnet_cidr = null
  # name - (optional) is a type of string
  name = null
  # network_id - (optional) is a type of string
  network_id = null
  # plane - (optional) is a type of string
  plane = null
  # region - (optional) is a type of string
  region = null
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

variable "matching_subnet_cidr" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "network_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "plane" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "ecl_network_network_v2" "this" {
  description          = var.description
  matching_subnet_cidr = var.matching_subnet_cidr
  name                 = var.name
  network_id           = var.network_id
  plane                = var.plane
  region               = var.region
}
```

[top](#index)

### Outputs

```terraform
output "admin_state_up" {
  description = "returns a bool"
  value       = data.ecl_network_network_v2.this.admin_state_up
}

output "description" {
  description = "returns a string"
  value       = data.ecl_network_network_v2.this.description
}

output "id" {
  description = "returns a string"
  value       = data.ecl_network_network_v2.this.id
}

output "matching_subnet_cidr" {
  description = "returns a string"
  value       = data.ecl_network_network_v2.this.matching_subnet_cidr
}

output "name" {
  description = "returns a string"
  value       = data.ecl_network_network_v2.this.name
}

output "network_id" {
  description = "returns a string"
  value       = data.ecl_network_network_v2.this.network_id
}

output "plane" {
  description = "returns a string"
  value       = data.ecl_network_network_v2.this.plane
}

output "region" {
  description = "returns a string"
  value       = data.ecl_network_network_v2.this.region
}

output "status" {
  description = "returns a string"
  value       = data.ecl_network_network_v2.this.status
}

output "subnets" {
  description = "returns a list of string"
  value       = data.ecl_network_network_v2.this.subnets
}

output "tags" {
  description = "returns a map of string"
  value       = data.ecl_network_network_v2.this.tags
}

output "tenant_id" {
  description = "returns a string"
  value       = data.ecl_network_network_v2.this.tenant_id
}

output "this" {
  value = ecl_network_network_v2.this
}
```

[top](#index)