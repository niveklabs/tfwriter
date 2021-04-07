# tencentcloud_vpc_acl

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
module "tencentcloud_vpc_acl" {
  source = "./modules/tencentcloud/r/tencentcloud_vpc_acl"

  # egress - (optional) is a type of list of string
  egress = []
  # ingress - (optional) is a type of list of string
  ingress = []
  # name - (required) is a type of string
  name = null
  # vpc_id - (required) is a type of string
  vpc_id = null
}
```

[top](#index)

### Variables

```terraform
variable "egress" {
  description = "(optional) - Egress rules. A rule must match the following format: [action]#[cidr_ip]#[port]#[protocol]. The available value of 'action' is `ACCEPT` and `DROP`. The 'cidr_ip' must be an IP address network or segment. The 'port' valid format is `80`, `80,443`, `80-90` or `ALL`. The available value of 'protocol' is `TCP`, `UDP`, `ICMP` and `ALL`. When 'protocol' is `ICMP` or `ALL`, the 'port' must be `ALL`."
  type        = list(string)
  default     = null
}

variable "ingress" {
  description = "(optional) - Ingress rules. A rule must match the following format: [action]#[cidr_ip]#[port]#[protocol]. The available value of 'action' is `ACCEPT` and `DROP`. The 'cidr_ip' must be an IP address network or segment. The 'port' valid format is `80`, `80,443`, `80-90` or `ALL`. The available value of 'protocol' is `TCP`, `UDP`, `ICMP` and `ALL`. When 'protocol' is `ICMP` or `ALL`, the 'port' must be `ALL`."
  type        = list(string)
  default     = null
}

variable "name" {
  description = "(required) - Name of the network ACL."
  type        = string
}

variable "vpc_id" {
  description = "(required) - ID of the VPC instance."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_vpc_acl" "this" {
  egress  = var.egress
  ingress = var.ingress
  name    = var.name
  vpc_id  = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = tencentcloud_vpc_acl.this.create_time
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_vpc_acl.this.id
}

output "this" {
  value = tencentcloud_vpc_acl.this
}
```

[top](#index)