# tencentcloud_clb_instance

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
module "tencentcloud_clb_instance" {
  source = "./modules/tencentcloud/r/tencentcloud_clb_instance"

  # address_ip_version - (optional) is a type of string
  address_ip_version = null
  # clb_name - (required) is a type of string
  clb_name = null
  # internet_bandwidth_max_out - (optional) is a type of number
  internet_bandwidth_max_out = null
  # internet_charge_type - (optional) is a type of string
  internet_charge_type = null
  # network_type - (required) is a type of string
  network_type = null
  # project_id - (optional) is a type of number
  project_id = null
  # security_groups - (optional) is a type of list of string
  security_groups = []
  # subnet_id - (optional) is a type of string
  subnet_id = null
  # tags - (optional) is a type of map of string
  tags = {}
  # target_region_info_region - (optional) is a type of string
  target_region_info_region = null
  # target_region_info_vpc_id - (optional) is a type of string
  target_region_info_vpc_id = null
  # vpc_id - (optional) is a type of string
  vpc_id = null
}
```

[top](#index)

### Variables

```terraform
variable "address_ip_version" {
  description = "(optional) - IP version, only applicable to open CLB. Valid values are `ipv4`, `ipv6` and `IPv6FullChain`."
  type        = string
  default     = null
}

variable "clb_name" {
  description = "(required) - Name of the CLB. The name can only contain Chinese characters, English letters, numbers, underscore and hyphen '-'."
  type        = string
}

variable "internet_bandwidth_max_out" {
  description = "(optional) - Max bandwidth out, only applicable to open CLB. Valid value ranges is [1, 2048]. Unit is MB."
  type        = number
  default     = null
}

variable "internet_charge_type" {
  description = "(optional) - Internet charge type, only applicable to open CLB. Valid values are `TRAFFIC_POSTPAID_BY_HOUR`, `BANDWIDTH_POSTPAID_BY_HOUR` and `BANDWIDTH_PACKAGE`."
  type        = string
  default     = null
}

variable "network_type" {
  description = "(required) - Type of CLB instance. Valid values: `OPEN` and `INTERNAL`."
  type        = string
}

variable "project_id" {
  description = "(optional) - ID of the project within the CLB instance, `0` - Default Project."
  type        = number
  default     = null
}

variable "security_groups" {
  description = "(optional) - Security groups of the CLB instance. Only supports `OPEN` CLBs."
  type        = list(string)
  default     = null
}

variable "subnet_id" {
  description = "(optional) - Subnet ID of the CLB. Effective only for CLB within the VPC. Only supports `INTERNAL` CLBs. Default is `ipv4`."
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - The available tags within this CLB."
  type        = map(string)
  default     = null
}

variable "target_region_info_region" {
  description = "(optional) - Region information of backend services are attached the CLB instance. Only supports `OPEN` CLBs."
  type        = string
  default     = null
}

variable "target_region_info_vpc_id" {
  description = "(optional) - Vpc information of backend services are attached the CLB instance. Only supports `OPEN` CLBs."
  type        = string
  default     = null
}

variable "vpc_id" {
  description = "(optional) - VPC ID of the CLB."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_clb_instance" "this" {
  address_ip_version         = var.address_ip_version
  clb_name                   = var.clb_name
  internet_bandwidth_max_out = var.internet_bandwidth_max_out
  internet_charge_type       = var.internet_charge_type
  network_type               = var.network_type
  project_id                 = var.project_id
  security_groups            = var.security_groups
  subnet_id                  = var.subnet_id
  tags                       = var.tags
  target_region_info_region  = var.target_region_info_region
  target_region_info_vpc_id  = var.target_region_info_vpc_id
  vpc_id                     = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "address_ip_version" {
  description = "returns a string"
  value       = tencentcloud_clb_instance.this.address_ip_version
}

output "clb_vips" {
  description = "returns a list of string"
  value       = tencentcloud_clb_instance.this.clb_vips
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_clb_instance.this.id
}

output "internet_bandwidth_max_out" {
  description = "returns a number"
  value       = tencentcloud_clb_instance.this.internet_bandwidth_max_out
}

output "internet_charge_type" {
  description = "returns a string"
  value       = tencentcloud_clb_instance.this.internet_charge_type
}

output "target_region_info_region" {
  description = "returns a string"
  value       = tencentcloud_clb_instance.this.target_region_info_region
}

output "target_region_info_vpc_id" {
  description = "returns a string"
  value       = tencentcloud_clb_instance.this.target_region_info_vpc_id
}

output "vip_isp" {
  description = "returns a string"
  value       = tencentcloud_clb_instance.this.vip_isp
}

output "vpc_id" {
  description = "returns a string"
  value       = tencentcloud_clb_instance.this.vpc_id
}

output "this" {
  value = tencentcloud_clb_instance.this
}
```

[top](#index)