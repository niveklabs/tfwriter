# tencentcloud_subnet

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
module "tencentcloud_subnet" {
  source = "./modules/tencentcloud/r/tencentcloud_subnet"

  # availability_zone - (required) is a type of string
  availability_zone = null
  # cidr_block - (required) is a type of string
  cidr_block = null
  # is_multicast - (optional) is a type of bool
  is_multicast = null
  # name - (required) is a type of string
  name = null
  # route_table_id - (optional) is a type of string
  route_table_id = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vpc_id - (required) is a type of string
  vpc_id = null
}
```

[top](#index)

### Variables

```terraform
variable "availability_zone" {
  description = "(required) - The availability zone within which the subnet should be created."
  type        = string
}

variable "cidr_block" {
  description = "(required) - A network address block of the subnet."
  type        = string
}

variable "is_multicast" {
  description = "(optional) - Indicates whether multicast is enabled. The default value is 'true'."
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - The name of subnet to be created."
  type        = string
}

variable "route_table_id" {
  description = "(optional) - ID of a routing table to which the subnet should be associated."
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - Tags of the subnet."
  type        = map(string)
  default     = null
}

variable "vpc_id" {
  description = "(required) - ID of the VPC to be associated."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_subnet" "this" {
  availability_zone = var.availability_zone
  cidr_block        = var.cidr_block
  is_multicast      = var.is_multicast
  name              = var.name
  route_table_id    = var.route_table_id
  tags              = var.tags
  vpc_id            = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "available_ip_count" {
  description = "returns a number"
  value       = tencentcloud_subnet.this.available_ip_count
}

output "create_time" {
  description = "returns a string"
  value       = tencentcloud_subnet.this.create_time
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_subnet.this.id
}

output "is_default" {
  description = "returns a bool"
  value       = tencentcloud_subnet.this.is_default
}

output "route_table_id" {
  description = "returns a string"
  value       = tencentcloud_subnet.this.route_table_id
}

output "this" {
  value = tencentcloud_subnet.this
}
```

[top](#index)