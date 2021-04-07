# tencentcloud_dcx

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tencentcloud = ">= 1.56.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tencentcloud_dcx" {
  source = "./modules/tencentcloud/r/tencentcloud_dcx"

  # bandwidth - (optional) is a type of number
  bandwidth = null
  # bgp_asn - (optional) is a type of number
  bgp_asn = null
  # bgp_auth_key - (optional) is a type of string
  bgp_auth_key = null
  # customer_address - (optional) is a type of string
  customer_address = null
  # dc_id - (required) is a type of string
  dc_id = null
  # dcg_id - (required) is a type of string
  dcg_id = null
  # name - (required) is a type of string
  name = null
  # network_type - (optional) is a type of string
  network_type = null
  # route_filter_prefixes - (optional) is a type of set of string
  route_filter_prefixes = []
  # route_type - (optional) is a type of string
  route_type = null
  # tencent_address - (optional) is a type of string
  tencent_address = null
  # vlan - (optional) is a type of number
  vlan = null
  # vpc_id - (required) is a type of string
  vpc_id = null
}
```

[top](#index)

### Variables

```terraform
variable "bandwidth" {
  description = "(optional) - Bandwidth of the DC."
  type        = number
  default     = null
}

variable "bgp_asn" {
  description = "(optional) - BGP ASN of the user. A required field within BGP."
  type        = number
  default     = null
}

variable "bgp_auth_key" {
  description = "(optional) - BGP key of the user."
  type        = string
  default     = null
}

variable "customer_address" {
  description = "(optional) - Interconnect IP of the DC within client."
  type        = string
  default     = null
}

variable "dc_id" {
  description = "(required) - ID of the DC to be queried, application deployment offline."
  type        = string
}

variable "dcg_id" {
  description = "(required) - ID of the DC Gateway. Currently only new in the console."
  type        = string
}

variable "name" {
  description = "(required) - Name of the dedicated tunnel."
  type        = string
}

variable "network_type" {
  description = "(optional) - Type of the network. Valid value: `VPC`, `BMVPC` and `CCN`. The default value is `VPC`."
  type        = string
  default     = null
}

variable "route_filter_prefixes" {
  description = "(optional) - Static route, the network address of the user IDC. It can be modified after setting but cannot be deleted. AN unable field within BGP."
  type        = set(string)
  default     = null
}

variable "route_type" {
  description = "(optional) - Type of the route, and available values include BGP and STATIC. The default value is `BGP`."
  type        = string
  default     = null
}

variable "tencent_address" {
  description = "(optional) - Interconnect IP of the DC within Tencent."
  type        = string
  default     = null
}

variable "vlan" {
  description = "(optional) - Vlan of the dedicated tunnels. Valid value ranges: (0~3000). `0` means that only one tunnel can be created for the physical connect."
  type        = number
  default     = null
}

variable "vpc_id" {
  description = "(required) - ID of the VPC or BMVPC."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_dcx" "this" {
  bandwidth             = var.bandwidth
  bgp_asn               = var.bgp_asn
  bgp_auth_key          = var.bgp_auth_key
  customer_address      = var.customer_address
  dc_id                 = var.dc_id
  dcg_id                = var.dcg_id
  name                  = var.name
  network_type          = var.network_type
  route_filter_prefixes = var.route_filter_prefixes
  route_type            = var.route_type
  tencent_address       = var.tencent_address
  vlan                  = var.vlan
  vpc_id                = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "bandwidth" {
  description = "returns a number"
  value       = tencentcloud_dcx.this.bandwidth
}

output "bgp_asn" {
  description = "returns a number"
  value       = tencentcloud_dcx.this.bgp_asn
}

output "create_time" {
  description = "returns a string"
  value       = tencentcloud_dcx.this.create_time
}

output "customer_address" {
  description = "returns a string"
  value       = tencentcloud_dcx.this.customer_address
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_dcx.this.id
}

output "state" {
  description = "returns a string"
  value       = tencentcloud_dcx.this.state
}

output "tencent_address" {
  description = "returns a string"
  value       = tencentcloud_dcx.this.tencent_address
}

output "this" {
  value = tencentcloud_dcx.this
}
```

[top](#index)