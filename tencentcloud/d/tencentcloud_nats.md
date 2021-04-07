# tencentcloud_nats

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
module "tencentcloud_nats" {
  source = "./modules/tencentcloud/d/tencentcloud_nats"

  # bandwidth - (optional) is a type of number
  bandwidth = null
  # max_concurrent - (optional) is a type of number
  max_concurrent = null
  # name - (optional) is a type of string
  name = null
  # state - (optional) is a type of number
  state = null
  # vpc_id - (optional) is a type of string
  vpc_id = null
}
```

[top](#index)

### Variables

```terraform
variable "bandwidth" {
  description = "(optional) - The maximum public network output bandwidth of the gateway (unit: Mbps), for example: `10`, `20`, `50`, `100`, `200`, `500`, `1000`, `2000`, `5000`."
  type        = number
  default     = null
}

variable "max_concurrent" {
  description = "(optional) - The upper limit of concurrent connection of NAT gateway, for example: `1000000`, `3000000`, `10000000`."
  type        = number
  default     = null
}

variable "name" {
  description = "(optional) - The name for NAT Gateway."
  type        = string
  default     = null
}

variable "state" {
  description = "(optional) - NAT gateway status. Valid values: 0, 1, 2. 0: Running, 1: Unavailable, 2: Be in arrears and out of service."
  type        = number
  default     = null
}

variable "vpc_id" {
  description = "(optional) - The VPC ID for NAT Gateway."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_nats" "this" {
  # bandwidth - (optional) is a type of number
  bandwidth = var.bandwidth
  # max_concurrent - (optional) is a type of number
  max_concurrent = var.max_concurrent
  # name - (optional) is a type of string
  name = var.name
  # state - (optional) is a type of number
  state = var.state
  # vpc_id - (optional) is a type of string
  vpc_id = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_nats.this.id
}

output "nats" {
  description = "returns a list of object"
  value       = data.tencentcloud_nats.this.nats
}

output "this" {
  value = tencentcloud_nats.this
}
```

[top](#index)