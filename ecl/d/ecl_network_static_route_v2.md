# ecl_network_static_route_v2

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
module "ecl_network_static_route_v2" {
  source = "./modules/ecl/d/ecl_network_static_route_v2"

  # aws_gw_id - (optional) is a type of string
  aws_gw_id = null
  # azure_gw_id - (optional) is a type of string
  azure_gw_id = null
  # description - (optional) is a type of string
  description = null
  # destination - (optional) is a type of string
  destination = null
  # gcp_gw_id - (optional) is a type of string
  gcp_gw_id = null
  # interdc_gw_id - (optional) is a type of string
  interdc_gw_id = null
  # internet_gw_id - (optional) is a type of string
  internet_gw_id = null
  # name - (optional) is a type of string
  name = null
  # nexthop - (optional) is a type of string
  nexthop = null
  # region - (optional) is a type of string
  region = null
  # service_type - (optional) is a type of string
  service_type = null
  # static_route_id - (optional) is a type of string
  static_route_id = null
  # status - (optional) is a type of string
  status = null
  # tenant_id - (optional) is a type of string
  tenant_id = null
  # vpn_gw_id - (optional) is a type of string
  vpn_gw_id = null
}
```

[top](#index)

### Variables

```terraform
variable "aws_gw_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "azure_gw_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "destination" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gcp_gw_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "interdc_gw_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "internet_gw_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "nexthop" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "static_route_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tenant_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vpn_gw_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "ecl_network_static_route_v2" "this" {
  aws_gw_id       = var.aws_gw_id
  azure_gw_id     = var.azure_gw_id
  description     = var.description
  destination     = var.destination
  gcp_gw_id       = var.gcp_gw_id
  interdc_gw_id   = var.interdc_gw_id
  internet_gw_id  = var.internet_gw_id
  name            = var.name
  nexthop         = var.nexthop
  region          = var.region
  service_type    = var.service_type
  static_route_id = var.static_route_id
  status          = var.status
  tenant_id       = var.tenant_id
  vpn_gw_id       = var.vpn_gw_id
}
```

[top](#index)

### Outputs

```terraform
output "aws_gw_id" {
  description = "returns a string"
  value       = data.ecl_network_static_route_v2.this.aws_gw_id
}

output "azure_gw_id" {
  description = "returns a string"
  value       = data.ecl_network_static_route_v2.this.azure_gw_id
}

output "description" {
  description = "returns a string"
  value       = data.ecl_network_static_route_v2.this.description
}

output "destination" {
  description = "returns a string"
  value       = data.ecl_network_static_route_v2.this.destination
}

output "gcp_gw_id" {
  description = "returns a string"
  value       = data.ecl_network_static_route_v2.this.gcp_gw_id
}

output "id" {
  description = "returns a string"
  value       = data.ecl_network_static_route_v2.this.id
}

output "interdc_gw_id" {
  description = "returns a string"
  value       = data.ecl_network_static_route_v2.this.interdc_gw_id
}

output "internet_gw_id" {
  description = "returns a string"
  value       = data.ecl_network_static_route_v2.this.internet_gw_id
}

output "name" {
  description = "returns a string"
  value       = data.ecl_network_static_route_v2.this.name
}

output "nexthop" {
  description = "returns a string"
  value       = data.ecl_network_static_route_v2.this.nexthop
}

output "region" {
  description = "returns a string"
  value       = data.ecl_network_static_route_v2.this.region
}

output "service_type" {
  description = "returns a string"
  value       = data.ecl_network_static_route_v2.this.service_type
}

output "static_route_id" {
  description = "returns a string"
  value       = data.ecl_network_static_route_v2.this.static_route_id
}

output "status" {
  description = "returns a string"
  value       = data.ecl_network_static_route_v2.this.status
}

output "tenant_id" {
  description = "returns a string"
  value       = data.ecl_network_static_route_v2.this.tenant_id
}

output "vpn_gw_id" {
  description = "returns a string"
  value       = data.ecl_network_static_route_v2.this.vpn_gw_id
}

output "this" {
  value = ecl_network_static_route_v2.this
}
```

[top](#index)