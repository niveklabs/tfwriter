# tencentcloud_vpn_gateways

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "tencentcloud_vpn_gateways" {
  source = "./modules/tencentcloud/d/tencentcloud_vpn_gateways"

  # name - (optional) is a type of string
  name = null
  # public_ip_address - (optional) is a type of string
  public_ip_address = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vpc_id - (optional) is a type of string
  vpc_id = null
  # zone - (optional) is a type of string
  zone = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - Name of the VPN gateway. The length of character is limited to 1-60."
  type        = string
  default     = null
}

variable "public_ip_address" {
  description = "(optional) - Public ip address of the VPN gateway."
  type        = string
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - Tags of the VPN gateway to be queried."
  type        = map(string)
  default     = null
}

variable "vpc_id" {
  description = "(optional) - ID of the VPC."
  type        = string
  default     = null
}

variable "zone" {
  description = "(optional) - Zone of the VPN gateway."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_vpn_gateways" "this" {
  name               = var.name
  public_ip_address  = var.public_ip_address
  result_output_file = var.result_output_file
  tags               = var.tags
  vpc_id             = var.vpc_id
  zone               = var.zone
}
```

[top](#index)

### Outputs

```terraform
output "gateway_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_vpn_gateways.this.gateway_list
}

output "id" {
  description = "returns a string"
  value       = data.tencentcloud_vpn_gateways.this.id
}

output "this" {
  value = tencentcloud_vpn_gateways.this
}
```

[top](#index)