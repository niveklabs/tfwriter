# tencentcloud_dc_gateway

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
module "tencentcloud_dc_gateway" {
  source = "./modules/tencentcloud/r/tencentcloud_dc_gateway"

  # gateway_type - (optional) is a type of string
  gateway_type = null
  # name - (required) is a type of string
  name = null
  # network_instance_id - (required) is a type of string
  network_instance_id = null
  # network_type - (required) is a type of string
  network_type = null
}
```

[top](#index)

### Variables

```terraform
variable "gateway_type" {
  description = "(optional) - Type of the gateway. Valid value: `NORMAL` and `NAT`. Default is `NORMAL`. NOTES: CCN only supports `NORMAL` and a VPC can create two DCGs, the one is NAT type and the other is non-NAT type."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name of the DCG."
  type        = string
}

variable "network_instance_id" {
  description = "(required) - If the `network_type` value is `VPC`, the available value is VPC ID. But when the `network_type` value is `CCN`, the available value is CCN instance ID."
  type        = string
}

variable "network_type" {
  description = "(required) - Type of associated network. Valid value: `VPC` and `CCN`."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_dc_gateway" "this" {
  # gateway_type - (optional) is a type of string
  gateway_type = var.gateway_type
  # name - (required) is a type of string
  name = var.name
  # network_instance_id - (required) is a type of string
  network_instance_id = var.network_instance_id
  # network_type - (required) is a type of string
  network_type = var.network_type
}
```

[top](#index)

### Outputs

```terraform
output "cnn_route_type" {
  description = "returns a string"
  value       = tencentcloud_dc_gateway.this.cnn_route_type
}

output "create_time" {
  description = "returns a string"
  value       = tencentcloud_dc_gateway.this.create_time
}

output "enable_bgp" {
  description = "returns a bool"
  value       = tencentcloud_dc_gateway.this.enable_bgp
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_dc_gateway.this.id
}

output "this" {
  value = tencentcloud_dc_gateway.this
}
```

[top](#index)