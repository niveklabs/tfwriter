# aws_elb

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "aws_elb" {
  source = "./modules/aws/r/aws_elb"

  # availability_zones - (optional) is a type of set of string
  availability_zones = []
  # connection_draining - (optional) is a type of bool
  connection_draining = null
  # connection_draining_timeout - (optional) is a type of number
  connection_draining_timeout = null
  # cross_zone_load_balancing - (optional) is a type of bool
  cross_zone_load_balancing = null
  # idle_timeout - (optional) is a type of number
  idle_timeout = null
  # instances - (optional) is a type of set of string
  instances = []
  # internal - (optional) is a type of bool
  internal = null
  # name - (optional) is a type of string
  name = null
  # name_prefix - (optional) is a type of string
  name_prefix = null
  # security_groups - (optional) is a type of set of string
  security_groups = []
  # source_security_group - (optional) is a type of string
  source_security_group = null
  # subnets - (optional) is a type of set of string
  subnets = []
  # tags - (optional) is a type of map of string
  tags = {}

  access_logs = [{
    bucket        = null
    bucket_prefix = null
    enabled       = null
    interval      = null
  }]

  health_check = [{
    healthy_threshold   = null
    interval            = null
    target              = null
    timeout             = null
    unhealthy_threshold = null
  }]

  listener = [{
    instance_port      = null
    instance_protocol  = null
    lb_port            = null
    lb_protocol        = null
    ssl_certificate_id = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "availability_zones" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "connection_draining" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "connection_draining_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "cross_zone_load_balancing" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "idle_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "instances" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "internal" {
  description = "(optional)"
  type        = bool
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

variable "source_security_group" {
  description = "(optional)"
  type        = string
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
      bucket        = string
      bucket_prefix = string
      enabled       = bool
      interval      = number
    }
  ))
  default = []
}

variable "health_check" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      healthy_threshold   = number
      interval            = number
      target              = string
      timeout             = number
      unhealthy_threshold = number
    }
  ))
  default = []
}

variable "listener" {
  description = "nested mode: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      instance_port      = number
      instance_protocol  = string
      lb_port            = number
      lb_protocol        = string
      ssl_certificate_id = string
    }
  ))
}
```

[top](#index)

### Resource

```hcl
resource "aws_elb" "this" {
  availability_zones          = var.availability_zones
  connection_draining         = var.connection_draining
  connection_draining_timeout = var.connection_draining_timeout
  cross_zone_load_balancing   = var.cross_zone_load_balancing
  idle_timeout                = var.idle_timeout
  instances                   = var.instances
  internal                    = var.internal
  name                        = var.name
  name_prefix                 = var.name_prefix
  security_groups             = var.security_groups
  source_security_group       = var.source_security_group
  subnets                     = var.subnets
  tags                        = var.tags

  dynamic "access_logs" {
    for_each = var.access_logs
    content {
      bucket        = access_logs.value["bucket"]
      bucket_prefix = access_logs.value["bucket_prefix"]
      enabled       = access_logs.value["enabled"]
      interval      = access_logs.value["interval"]
    }
  }

  dynamic "health_check" {
    for_each = var.health_check
    content {
      healthy_threshold   = health_check.value["healthy_threshold"]
      interval            = health_check.value["interval"]
      target              = health_check.value["target"]
      timeout             = health_check.value["timeout"]
      unhealthy_threshold = health_check.value["unhealthy_threshold"]
    }
  }

  dynamic "listener" {
    for_each = var.listener
    content {
      instance_port      = listener.value["instance_port"]
      instance_protocol  = listener.value["instance_protocol"]
      lb_port            = listener.value["lb_port"]
      lb_protocol        = listener.value["lb_protocol"]
      ssl_certificate_id = listener.value["ssl_certificate_id"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = aws_elb.this.arn
}

output "availability_zones" {
  description = "returns a set of string"
  value       = aws_elb.this.availability_zones
}

output "dns_name" {
  description = "returns a string"
  value       = aws_elb.this.dns_name
}

output "id" {
  description = "returns a string"
  value       = aws_elb.this.id
}

output "instances" {
  description = "returns a set of string"
  value       = aws_elb.this.instances
}

output "internal" {
  description = "returns a bool"
  value       = aws_elb.this.internal
}

output "name" {
  description = "returns a string"
  value       = aws_elb.this.name
}

output "security_groups" {
  description = "returns a set of string"
  value       = aws_elb.this.security_groups
}

output "source_security_group" {
  description = "returns a string"
  value       = aws_elb.this.source_security_group
}

output "source_security_group_id" {
  description = "returns a string"
  value       = aws_elb.this.source_security_group_id
}

output "subnets" {
  description = "returns a set of string"
  value       = aws_elb.this.subnets
}

output "zone_id" {
  description = "returns a string"
  value       = aws_elb.this.zone_id
}

output "this" {
  value = aws_elb.this
}
```

[top](#index)