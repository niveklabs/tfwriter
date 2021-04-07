# tencentcloud_nat_gateway

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
module "tencentcloud_nat_gateway" {
  source = "./modules/tencentcloud/r/tencentcloud_nat_gateway"

  # assigned_eip_set - (required) is a type of set of string
  assigned_eip_set = []
  # bandwidth - (optional) is a type of number
  bandwidth = null
  # max_concurrent - (optional) is a type of number
  max_concurrent = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vpc_id - (required) is a type of string
  vpc_id = null
}
```

[top](#index)

### Variables

```terraform
variable "assigned_eip_set" {
  description = "(required) - EIP IP address set bound to the gateway. The value of at least 1 and at most 10."
  type        = set(string)
}

variable "bandwidth" {
  description = "(optional) - The maximum public network output bandwidth of NAT gateway (unit: Mbps). Valid values: `20`, `50`, `100`, `200`, `500`, `1000`, `2000`, `5000`. Default is 100."
  type        = number
  default     = null
}

variable "max_concurrent" {
  description = "(optional) - The upper limit of concurrent connection of NAT gateway. Valid values: `1000000`, `3000000`, `10000000`. Default is `1000000`."
  type        = number
  default     = null
}

variable "name" {
  description = "(required) - Name of the NAT gateway."
  type        = string
}

variable "tags" {
  description = "(optional) - The available tags within this NAT gateway."
  type        = map(string)
  default     = null
}

variable "vpc_id" {
  description = "(required) - ID of the vpc."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_nat_gateway" "this" {
  assigned_eip_set = var.assigned_eip_set
  bandwidth        = var.bandwidth
  max_concurrent   = var.max_concurrent
  name             = var.name
  tags             = var.tags
  vpc_id           = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "created_time" {
  description = "returns a string"
  value       = tencentcloud_nat_gateway.this.created_time
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_nat_gateway.this.id
}

output "this" {
  value = tencentcloud_nat_gateway.this
}
```

[top](#index)