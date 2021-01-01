# aws_alb

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "aws_alb" {
  source = "./modules/aws/r/aws_alb"

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

```hcl
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
  description = "nested mode: NestingList, min items: 0, max items: 1"
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
  description = "nested mode: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      allocation_id        = string
      outpost_id           = string
      private_ipv4_address = string
      subnet_id            = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
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

```hcl
resource "aws_alb" "this" {
  customer_owned_ipv4_pool         = var.customer_owned_ipv4_pool
  drop_invalid_header_fields       = var.drop_invalid_header_fields
  enable_cross_zone_load_balancing = var.enable_cross_zone_load_balancing
  enable_deletion_protection       = var.enable_deletion_protection
  enable_http2                     = var.enable_http2
  idle_timeout                     = var.idle_timeout
  internal                         = var.internal
  ip_address_type                  = var.ip_address_type
  load_balancer_type               = var.load_balancer_type
  name                             = var.name
  name_prefix                      = var.name_prefix
  security_groups                  = var.security_groups
  subnets                          = var.subnets
  tags                             = var.tags

  dynamic "access_logs" {
    for_each = var.access_logs
    content {
      bucket  = access_logs.value["bucket"]
      enabled = access_logs.value["enabled"]
      prefix  = access_logs.value["prefix"]
    }
  }

  dynamic "subnet_mapping" {
    for_each = var.subnet_mapping
    content {
      allocation_id        = subnet_mapping.value["allocation_id"]
      private_ipv4_address = subnet_mapping.value["private_ipv4_address"]
      subnet_id            = subnet_mapping.value["subnet_id"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = aws_alb.this.arn
}

output "arn_suffix" {
  description = "returns a string"
  value       = aws_alb.this.arn_suffix
}

output "dns_name" {
  description = "returns a string"
  value       = aws_alb.this.dns_name
}

output "id" {
  description = "returns a string"
  value       = aws_alb.this.id
}

output "internal" {
  description = "returns a bool"
  value       = aws_alb.this.internal
}

output "ip_address_type" {
  description = "returns a string"
  value       = aws_alb.this.ip_address_type
}

output "name" {
  description = "returns a string"
  value       = aws_alb.this.name
}

output "security_groups" {
  description = "returns a set of string"
  value       = aws_alb.this.security_groups
}

output "subnets" {
  description = "returns a set of string"
  value       = aws_alb.this.subnets
}

output "vpc_id" {
  description = "returns a string"
  value       = aws_alb.this.vpc_id
}

output "zone_id" {
  description = "returns a string"
  value       = aws_alb.this.zone_id
}

output "this" {
  value = aws_alb.this
}
```

[top](#index)