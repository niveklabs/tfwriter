# tencentcloud_vpc

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
module "tencentcloud_vpc" {
  source = "./modules/tencentcloud/r/tencentcloud_vpc"

  # cidr_block - (required) is a type of string
  cidr_block = null
  # dns_servers - (optional) is a type of set of string
  dns_servers = []
  # is_multicast - (optional) is a type of bool
  is_multicast = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "cidr_block" {
  description = "(required) - A network address block which should be a subnet of the three internal network segments (10.0.0.0/16, 172.16.0.0/12 and 192.168.0.0/16)."
  type        = string
}

variable "dns_servers" {
  description = "(optional) - The DNS server list of the VPC. And you can specify 0 to 5 servers to this list."
  type        = set(string)
  default     = null
}

variable "is_multicast" {
  description = "(optional) - Indicates whether VPC multicast is enabled. The default value is 'true'."
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - The name of the VPC."
  type        = string
}

variable "tags" {
  description = "(optional) - Tags of the VPC."
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_vpc" "this" {
  # cidr_block - (required) is a type of string
  cidr_block = var.cidr_block
  # dns_servers - (optional) is a type of set of string
  dns_servers = var.dns_servers
  # is_multicast - (optional) is a type of bool
  is_multicast = var.is_multicast
  # name - (required) is a type of string
  name = var.name
  # tags - (optional) is a type of map of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = tencentcloud_vpc.this.create_time
}

output "dns_servers" {
  description = "returns a set of string"
  value       = tencentcloud_vpc.this.dns_servers
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_vpc.this.id
}

output "is_default" {
  description = "returns a bool"
  value       = tencentcloud_vpc.this.is_default
}

output "this" {
  value = tencentcloud_vpc.this
}
```

[top](#index)