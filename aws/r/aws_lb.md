# aws_lb

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_lb" {
  source = "./modules/aws/r/aws_lb"

  # customer_owned_ipv4_pool - (optional) is a type of string
  customer_owned_ipv4_pool = null
  # drop_invalid_header_fields - (optional) is a type of bool
  drop_invalid_header_fields = null
  # enable_cross_zone_load_balancing - (optional) is a type of bool
  enable_cross_zone_load_balancing = null
  # enable_deletion_protection - (optional) is a type of bool
  enable_deletion_protection = null
  # enable_http2 - (optional) is a type of bool
  enable_http2 = null
  # idle_timeout - (optional) is a type of number
  idle_timeout = null
  # internal - (optional) is a type of bool
  internal = null
  # ip_address_type - (optional) is a type of string
  ip_address_type = null
  # load_balancer_type - (optional) is a type of string
  load_balancer_type = null
  # name - (optional) is a type of string
  name = null
  # name_prefix - (optional) is a type of string
  name_prefix = null
  # security_groups - (optional) is a type of set of string
  security_groups = []
  # subnets - (optional) is a type of set of string
  subnets = []
  # tags - (optional) is a type of map of string
  tags = {}

  access_logs = [{
    bucket  = null
    enabled = null
    prefix  = null
  }]

  subnet_mapping = [{
    allocation_id        = null
    ipv6_address         = null
    outpost_id           = null
    private_ipv4_address = null
    subnet_id            = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "customer_owned_ipv4_pool" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "drop_invalid_header_fields" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_cross_zone_load_balancing" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_deletion_protection" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_http2" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "idle_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "internal" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ip_address_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "load_balancer_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_groups" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "subnets" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "access_logs" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      bucket  = string
      enabled = bool
      prefix  = string
    }
  ))
  default = []
}

variable "subnet_mapping" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      allocation_id        = string
      ipv6_address         = string
      outpost_id           = string
      private_ipv4_address = string
      subnet_id            = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_lb" "this" {
  # customer_owned_ipv4_pool - (optional) is a type of string
  customer_owned_ipv4_pool = var.customer_owned_ipv4_pool
  # drop_invalid_header_fields - (optional) is a type of bool
  drop_invalid_header_fields = var.drop_invalid_header_fields
  # enable_cross_zone_load_balancing - (optional) is a type of bool
  enable_cross_zone_load_balancing = var.enable_cross_zone_load_balancing
  # enable_deletion_protection - (optional) is a type of bool
  enable_deletion_protection = var.enable_deletion_protection
  # enable_http2 - (optional) is a type of bool
  enable_http2 = var.enable_http2
  # idle_timeout - (optional) is a type of number
  idle_timeout = var.idle_timeout
  # internal - (optional) is a type of bool
  internal = var.internal
  # ip_address_type - (optional) is a type of string
  ip_address_type = var.ip_address_type
  # load_balancer_type - (optional) is a type of string
  load_balancer_type = var.load_balancer_type
  # name - (optional) is a type of string
  name = var.name
  # name_prefix - (optional) is a type of string
  name_prefix = var.name_prefix
  # security_groups - (optional) is a type of set of string
  security_groups = var.security_groups
  # subnets - (optional) is a type of set of string
  subnets = var.subnets
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "access_logs" {
    for_each = var.access_logs
    content {
      # bucket - (required) is a type of string
      bucket = access_logs.value["bucket"]
      # enabled - (optional) is a type of bool
      enabled = access_logs.value["enabled"]
      # prefix - (optional) is a type of string
      prefix = access_logs.value["prefix"]
    }
  }

  dynamic "subnet_mapping" {
    for_each = var.subnet_mapping
    content {
      # allocation_id - (optional) is a type of string
      allocation_id = subnet_mapping.value["allocation_id"]
      # ipv6_address - (optional) is a type of string
      ipv6_address = subnet_mapping.value["ipv6_address"]
      # private_ipv4_address - (optional) is a type of string
      private_ipv4_address = subnet_mapping.value["private_ipv4_address"]
      # subnet_id - (required) is a type of string
      subnet_id = subnet_mapping.value["subnet_id"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_lb.this.arn
}

output "arn_suffix" {
  description = "returns a string"
  value       = aws_lb.this.arn_suffix
}

output "dns_name" {
  description = "returns a string"
  value       = aws_lb.this.dns_name
}

output "id" {
  description = "returns a string"
  value       = aws_lb.this.id
}

output "internal" {
  description = "returns a bool"
  value       = aws_lb.this.internal
}

output "ip_address_type" {
  description = "returns a string"
  value       = aws_lb.this.ip_address_type
}

output "name" {
  description = "returns a string"
  value       = aws_lb.this.name
}

output "security_groups" {
  description = "returns a set of string"
  value       = aws_lb.this.security_groups
}

output "subnets" {
  description = "returns a set of string"
  value       = aws_lb.this.subnets
}

output "vpc_id" {
  description = "returns a string"
  value       = aws_lb.this.vpc_id
}

output "zone_id" {
  description = "returns a string"
  value       = aws_lb.this.zone_id
}

output "this" {
  value = aws_lb.this
}
```

[top](#index)