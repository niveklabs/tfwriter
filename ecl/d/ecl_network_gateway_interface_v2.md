# ecl_network_gateway_interface_v2

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
    ecl = ">= 2.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ecl_network_gateway_interface_v2" {
  source = "./modules/ecl/d/ecl_network_gateway_interface_v2"

  # aws_gw_id - (optional) is a type of string
  aws_gw_id = null
  # azure_gw_id - (optional) is a type of string
  azure_gw_id = null
  # description - (optional) is a type of string
  description = null
  # gateway_interface_id - (optional) is a type of string
  gateway_interface_id = null
  # gcp_gw_id - (optional) is a type of string
  gcp_gw_id = null
  # gw_vipv4 - (optional) is a type of string
  gw_vipv4 = null
  # gw_vipv6 - (optional) is a type of string
  gw_vipv6 = null
  # interdc_gw_id - (optional) is a type of string
  interdc_gw_id = null
  # internet_gw_id - (optional) is a type of string
  internet_gw_id = null
  # name - (optional) is a type of string
  name = null
  # netmask - (optional) is a type of number
  netmask = null
  # network_id - (optional) is a type of string
  network_id = null
  # primary_ipv4 - (optional) is a type of string
  primary_ipv4 = null
  # primary_ipv6 - (optional) is a type of string
  primary_ipv6 = null
  # region - (optional) is a type of string
  region = null
  # secondary_ipv4 - (optional) is a type of string
  secondary_ipv4 = null
  # secondary_ipv6 - (optional) is a type of string
  secondary_ipv6 = null
  # service_type - (optional) is a type of string
  service_type = null
  # status - (optional) is a type of string
  status = null
  # tenant_id - (optional) is a type of string
  tenant_id = null
  # vpn_gw_id - (optional) is a type of string
  vpn_gw_id = null
  # vrid - (optional) is a type of number
  vrid = null
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

variable "gateway_interface_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gcp_gw_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gw_vipv4" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gw_vipv6" {
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

variable "netmask" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "network_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "primary_ipv4" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "primary_ipv6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "secondary_ipv4" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "secondary_ipv6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_type" {
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

variable "vrid" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "ecl_network_gateway_interface_v2" "this" {
  # aws_gw_id - (optional) is a type of string
  aws_gw_id = var.aws_gw_id
  # azure_gw_id - (optional) is a type of string
  azure_gw_id = var.azure_gw_id
  # description - (optional) is a type of string
  description = var.description
  # gateway_interface_id - (optional) is a type of string
  gateway_interface_id = var.gateway_interface_id
  # gcp_gw_id - (optional) is a type of string
  gcp_gw_id = var.gcp_gw_id
  # gw_vipv4 - (optional) is a type of string
  gw_vipv4 = var.gw_vipv4
  # gw_vipv6 - (optional) is a type of string
  gw_vipv6 = var.gw_vipv6
  # interdc_gw_id - (optional) is a type of string
  interdc_gw_id = var.interdc_gw_id
  # internet_gw_id - (optional) is a type of string
  internet_gw_id = var.internet_gw_id
  # name - (optional) is a type of string
  name = var.name
  # netmask - (optional) is a type of number
  netmask = var.netmask
  # network_id - (optional) is a type of string
  network_id = var.network_id
  # primary_ipv4 - (optional) is a type of string
  primary_ipv4 = var.primary_ipv4
  # primary_ipv6 - (optional) is a type of string
  primary_ipv6 = var.primary_ipv6
  # region - (optional) is a type of string
  region = var.region
  # secondary_ipv4 - (optional) is a type of string
  secondary_ipv4 = var.secondary_ipv4
  # secondary_ipv6 - (optional) is a type of string
  secondary_ipv6 = var.secondary_ipv6
  # service_type - (optional) is a type of string
  service_type = var.service_type
  # status - (optional) is a type of string
  status = var.status
  # tenant_id - (optional) is a type of string
  tenant_id = var.tenant_id
  # vpn_gw_id - (optional) is a type of string
  vpn_gw_id = var.vpn_gw_id
  # vrid - (optional) is a type of number
  vrid = var.vrid
}
```

[top](#index)

### Outputs

```terraform
output "aws_gw_id" {
  description = "returns a string"
  value       = data.ecl_network_gateway_interface_v2.this.aws_gw_id
}

output "azure_gw_id" {
  description = "returns a string"
  value       = data.ecl_network_gateway_interface_v2.this.azure_gw_id
}

output "description" {
  description = "returns a string"
  value       = data.ecl_network_gateway_interface_v2.this.description
}

output "gateway_interface_id" {
  description = "returns a string"
  value       = data.ecl_network_gateway_interface_v2.this.gateway_interface_id
}

output "gcp_gw_id" {
  description = "returns a string"
  value       = data.ecl_network_gateway_interface_v2.this.gcp_gw_id
}

output "gw_vipv4" {
  description = "returns a string"
  value       = data.ecl_network_gateway_interface_v2.this.gw_vipv4
}

output "gw_vipv6" {
  description = "returns a string"
  value       = data.ecl_network_gateway_interface_v2.this.gw_vipv6
}

output "id" {
  description = "returns a string"
  value       = data.ecl_network_gateway_interface_v2.this.id
}

output "interdc_gw_id" {
  description = "returns a string"
  value       = data.ecl_network_gateway_interface_v2.this.interdc_gw_id
}

output "internet_gw_id" {
  description = "returns a string"
  value       = data.ecl_network_gateway_interface_v2.this.internet_gw_id
}

output "name" {
  description = "returns a string"
  value       = data.ecl_network_gateway_interface_v2.this.name
}

output "netmask" {
  description = "returns a number"
  value       = data.ecl_network_gateway_interface_v2.this.netmask
}

output "network_id" {
  description = "returns a string"
  value       = data.ecl_network_gateway_interface_v2.this.network_id
}

output "primary_ipv4" {
  description = "returns a string"
  value       = data.ecl_network_gateway_interface_v2.this.primary_ipv4
}

output "primary_ipv6" {
  description = "returns a string"
  value       = data.ecl_network_gateway_interface_v2.this.primary_ipv6
}

output "region" {
  description = "returns a string"
  value       = data.ecl_network_gateway_interface_v2.this.region
}

output "secondary_ipv4" {
  description = "returns a string"
  value       = data.ecl_network_gateway_interface_v2.this.secondary_ipv4
}

output "secondary_ipv6" {
  description = "returns a string"
  value       = data.ecl_network_gateway_interface_v2.this.secondary_ipv6
}

output "service_type" {
  description = "returns a string"
  value       = data.ecl_network_gateway_interface_v2.this.service_type
}

output "tenant_id" {
  description = "returns a string"
  value       = data.ecl_network_gateway_interface_v2.this.tenant_id
}

output "vpn_gw_id" {
  description = "returns a string"
  value       = data.ecl_network_gateway_interface_v2.this.vpn_gw_id
}

output "vrid" {
  description = "returns a number"
  value       = data.ecl_network_gateway_interface_v2.this.vrid
}

output "this" {
  value = ecl_network_gateway_interface_v2.this
}
```

[top](#index)