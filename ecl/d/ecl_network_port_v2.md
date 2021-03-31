# ecl_network_port_v2

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
module "ecl_network_port_v2" {
  source = "./modules/ecl/d/ecl_network_port_v2"

  # description - (optional) is a type of string
  description = null
  # device_id - (optional) is a type of string
  device_id = null
  # device_owner - (optional) is a type of string
  device_owner = null
  # mac_address - (optional) is a type of string
  mac_address = null
  # name - (optional) is a type of string
  name = null
  # network_id - (optional) is a type of string
  network_id = null
  # port_id - (optional) is a type of string
  port_id = null
  # region - (optional) is a type of string
  region = null
  # segmentation_id - (optional) is a type of number
  segmentation_id = null
  # segmentation_type - (optional) is a type of string
  segmentation_type = null
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

variable "device_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "device_owner" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mac_address" {
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

variable "port_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "segmentation_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "segmentation_type" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "ecl_network_port_v2" "this" {
  description       = var.description
  device_id         = var.device_id
  device_owner      = var.device_owner
  mac_address       = var.mac_address
  name              = var.name
  network_id        = var.network_id
  port_id           = var.port_id
  region            = var.region
  segmentation_id   = var.segmentation_id
  segmentation_type = var.segmentation_type
}
```

[top](#index)

### Outputs

```terraform
output "admin_state_up" {
  description = "returns a bool"
  value       = data.ecl_network_port_v2.this.admin_state_up
}

output "all_fixed_ips" {
  description = "returns a list of string"
  value       = data.ecl_network_port_v2.this.all_fixed_ips
}

output "allowed_address_pairs" {
  description = "returns a set of object"
  value       = data.ecl_network_port_v2.this.allowed_address_pairs
}

output "description" {
  description = "returns a string"
  value       = data.ecl_network_port_v2.this.description
}

output "device_id" {
  description = "returns a string"
  value       = data.ecl_network_port_v2.this.device_id
}

output "device_owner" {
  description = "returns a string"
  value       = data.ecl_network_port_v2.this.device_owner
}

output "fixed_ip" {
  description = "returns a list of object"
  value       = data.ecl_network_port_v2.this.fixed_ip
}

output "id" {
  description = "returns a string"
  value       = data.ecl_network_port_v2.this.id
}

output "mac_address" {
  description = "returns a string"
  value       = data.ecl_network_port_v2.this.mac_address
}

output "managed_by_service" {
  description = "returns a bool"
  value       = data.ecl_network_port_v2.this.managed_by_service
}

output "name" {
  description = "returns a string"
  value       = data.ecl_network_port_v2.this.name
}

output "network_id" {
  description = "returns a string"
  value       = data.ecl_network_port_v2.this.network_id
}

output "port_id" {
  description = "returns a string"
  value       = data.ecl_network_port_v2.this.port_id
}

output "region" {
  description = "returns a string"
  value       = data.ecl_network_port_v2.this.region
}

output "segmentation_id" {
  description = "returns a number"
  value       = data.ecl_network_port_v2.this.segmentation_id
}

output "segmentation_type" {
  description = "returns a string"
  value       = data.ecl_network_port_v2.this.segmentation_type
}

output "status" {
  description = "returns a string"
  value       = data.ecl_network_port_v2.this.status
}

output "tags" {
  description = "returns a map of string"
  value       = data.ecl_network_port_v2.this.tags
}

output "tenant_id" {
  description = "returns a string"
  value       = data.ecl_network_port_v2.this.tenant_id
}

output "this" {
  value = ecl_network_port_v2.this
}
```

[top](#index)