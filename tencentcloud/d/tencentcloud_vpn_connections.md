# tencentcloud_vpn_connections

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
module "tencentcloud_vpn_connections" {
  source = "./modules/tencentcloud/d/tencentcloud_vpn_connections"

  # customer_gateway_id - (optional) is a type of string
  customer_gateway_id = null
  # name - (optional) is a type of string
  name = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vpc_id - (optional) is a type of string
  vpc_id = null
  # vpn_gateway_id - (optional) is a type of string
  vpn_gateway_id = null
}
```

[top](#index)

### Variables

```terraform
variable "customer_gateway_id" {
  description = "(optional) - Customer gateway ID of the VPN connection."
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - Name of the VPN connection. The length of character is limited to 1-60."
  type        = string
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - Tags of the VPN connection to be queried."
  type        = map(string)
  default     = null
}

variable "vpc_id" {
  description = "(optional) - ID of the VPC."
  type        = string
  default     = null
}

variable "vpn_gateway_id" {
  description = "(optional) - VPN gateway ID of the VPN connection."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_vpn_connections" "this" {
  customer_gateway_id = var.customer_gateway_id
  name                = var.name
  result_output_file  = var.result_output_file
  tags                = var.tags
  vpc_id              = var.vpc_id
  vpn_gateway_id      = var.vpn_gateway_id
}
```

[top](#index)

### Outputs

```terraform
output "connection_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_vpn_connections.this.connection_list
}

output "id" {
  description = "returns a string"
  value       = data.tencentcloud_vpn_connections.this.id
}

output "this" {
  value = tencentcloud_vpn_connections.this
}
```

[top](#index)