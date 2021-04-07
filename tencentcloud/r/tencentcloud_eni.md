# tencentcloud_eni

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
module "tencentcloud_eni" {
  source = "./modules/tencentcloud/r/tencentcloud_eni"

  # description - (optional) is a type of string
  description = null
  # ipv4_count - (optional) is a type of number
  ipv4_count = null
  # name - (required) is a type of string
  name = null
  # security_groups - (optional) is a type of set of string
  security_groups = []
  # subnet_id - (required) is a type of string
  subnet_id = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vpc_id - (required) is a type of string
  vpc_id = null

  ipv4s = [{
    description = null
    ip          = null
    primary     = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description of the ENI, maximum length 60."
  type        = string
  default     = null
}

variable "ipv4_count" {
  description = "(optional) - The number of intranet IPv4s. When it is greater than 1, there is only one primary intranet IP. The others are auxiliary intranet IPs, which conflict with `ipv4s`."
  type        = number
  default     = null
}

variable "name" {
  description = "(required) - Name of the ENI, maximum length 60."
  type        = string
}

variable "security_groups" {
  description = "(optional) - A set of security group IDs."
  type        = set(string)
  default     = null
}

variable "subnet_id" {
  description = "(required) - ID of the subnet within this vpc."
  type        = string
}

variable "tags" {
  description = "(optional) - Tags of the ENI."
  type        = map(string)
  default     = null
}

variable "vpc_id" {
  description = "(required) - ID of the vpc."
  type        = string
}

variable "ipv4s" {
  description = "nested block: NestingSet, min items: 0, max items: 30"
  type = set(object(
    {
      description = string
      ip          = string
      primary     = bool
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_eni" "this" {
  # description - (optional) is a type of string
  description = var.description
  # ipv4_count - (optional) is a type of number
  ipv4_count = var.ipv4_count
  # name - (required) is a type of string
  name = var.name
  # security_groups - (optional) is a type of set of string
  security_groups = var.security_groups
  # subnet_id - (required) is a type of string
  subnet_id = var.subnet_id
  # tags - (optional) is a type of map of string
  tags = var.tags
  # vpc_id - (required) is a type of string
  vpc_id = var.vpc_id

  dynamic "ipv4s" {
    for_each = var.ipv4s
    content {
      # description - (optional) is a type of string
      description = ipv4s.value["description"]
      # ip - (required) is a type of string
      ip = ipv4s.value["ip"]
      # primary - (required) is a type of bool
      primary = ipv4s.value["primary"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = tencentcloud_eni.this.create_time
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_eni.this.id
}

output "ipv4_info" {
  description = "returns a list of object"
  value       = tencentcloud_eni.this.ipv4_info
}

output "mac" {
  description = "returns a string"
  value       = tencentcloud_eni.this.mac
}

output "primary" {
  description = "returns a bool"
  value       = tencentcloud_eni.this.primary
}

output "state" {
  description = "returns a string"
  value       = tencentcloud_eni.this.state
}

output "this" {
  value = tencentcloud_eni.this
}
```

[top](#index)