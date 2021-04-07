# tencentcloud_route_table_entry

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
module "tencentcloud_route_table_entry" {
  source = "./modules/tencentcloud/r/tencentcloud_route_table_entry"

  # description - (optional) is a type of string
  description = null
  # destination_cidr_block - (required) is a type of string
  destination_cidr_block = null
  # next_hub - (required) is a type of string
  next_hub = null
  # next_type - (required) is a type of string
  next_type = null
  # route_table_id - (required) is a type of string
  route_table_id = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description of the routing table entry."
  type        = string
  default     = null
}

variable "destination_cidr_block" {
  description = "(required) - Destination address block."
  type        = string
}

variable "next_hub" {
  description = "(required) - ID of next-hop gateway. Note: when `next_type` is EIP, GatewayId should be `0`."
  type        = string
}

variable "next_type" {
  description = "(required) - Type of next-hop. Valid values: `CVM`, `VPN`, `DIRECTCONNECT`, `PEERCONNECTION`, `SSLVPN`, `NAT`, `NORMAL_CVM`, `EIP` and `CCN`."
  type        = string
}

variable "route_table_id" {
  description = "(required) - ID of routing table to which this entry belongs."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_route_table_entry" "this" {
  description            = var.description
  destination_cidr_block = var.destination_cidr_block
  next_hub               = var.next_hub
  next_type              = var.next_type
  route_table_id         = var.route_table_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_route_table_entry.this.id
}

output "this" {
  value = tencentcloud_route_table_entry.this
}
```

[top](#index)