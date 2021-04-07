# aws_route53_record

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
module "aws_route53_record" {
  source = "./modules/aws/r/aws_route53_record"

  # allow_overwrite - (optional) is a type of bool
  allow_overwrite = null
  # health_check_id - (optional) is a type of string
  health_check_id = null
  # multivalue_answer_routing_policy - (optional) is a type of bool
  multivalue_answer_routing_policy = null
  # name - (required) is a type of string
  name = null
  # records - (optional) is a type of set of string
  records = []
  # set_identifier - (optional) is a type of string
  set_identifier = null
  # ttl - (optional) is a type of number
  ttl = null
  # type - (required) is a type of string
  type = null
  # zone_id - (required) is a type of string
  zone_id = null

  alias = [{
    evaluate_target_health = null
    name                   = null
    zone_id                = null
  }]

  failover_routing_policy = [{
    type = null
  }]

  geolocation_routing_policy = [{
    continent   = null
    country     = null
    subdivision = null
  }]

  latency_routing_policy = [{
    region = null
  }]

  weighted_routing_policy = [{
    weight = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "allow_overwrite" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "health_check_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "multivalue_answer_routing_policy" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "records" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "set_identifier" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "zone_id" {
  description = "(required)"
  type        = string
}

variable "alias" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      evaluate_target_health = bool
      name                   = string
      zone_id                = string
    }
  ))
  default = []
}

variable "failover_routing_policy" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      type = string
    }
  ))
  default = []
}

variable "geolocation_routing_policy" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      continent   = string
      country     = string
      subdivision = string
    }
  ))
  default = []
}

variable "latency_routing_policy" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      region = string
    }
  ))
  default = []
}

variable "weighted_routing_policy" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      weight = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_route53_record" "this" {
  # allow_overwrite - (optional) is a type of bool
  allow_overwrite = var.allow_overwrite
  # health_check_id - (optional) is a type of string
  health_check_id = var.health_check_id
  # multivalue_answer_routing_policy - (optional) is a type of bool
  multivalue_answer_routing_policy = var.multivalue_answer_routing_policy
  # name - (required) is a type of string
  name = var.name
  # records - (optional) is a type of set of string
  records = var.records
  # set_identifier - (optional) is a type of string
  set_identifier = var.set_identifier
  # ttl - (optional) is a type of number
  ttl = var.ttl
  # type - (required) is a type of string
  type = var.type
  # zone_id - (required) is a type of string
  zone_id = var.zone_id

  dynamic "alias" {
    for_each = var.alias
    content {
      # evaluate_target_health - (required) is a type of bool
      evaluate_target_health = alias.value["evaluate_target_health"]
      # name - (required) is a type of string
      name = alias.value["name"]
      # zone_id - (required) is a type of string
      zone_id = alias.value["zone_id"]
    }
  }

  dynamic "failover_routing_policy" {
    for_each = var.failover_routing_policy
    content {
      # type - (required) is a type of string
      type = failover_routing_policy.value["type"]
    }
  }

  dynamic "geolocation_routing_policy" {
    for_each = var.geolocation_routing_policy
    content {
      # continent - (optional) is a type of string
      continent = geolocation_routing_policy.value["continent"]
      # country - (optional) is a type of string
      country = geolocation_routing_policy.value["country"]
      # subdivision - (optional) is a type of string
      subdivision = geolocation_routing_policy.value["subdivision"]
    }
  }

  dynamic "latency_routing_policy" {
    for_each = var.latency_routing_policy
    content {
      # region - (required) is a type of string
      region = latency_routing_policy.value["region"]
    }
  }

  dynamic "weighted_routing_policy" {
    for_each = var.weighted_routing_policy
    content {
      # weight - (required) is a type of number
      weight = weighted_routing_policy.value["weight"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "allow_overwrite" {
  description = "returns a bool"
  value       = aws_route53_record.this.allow_overwrite
}

output "fqdn" {
  description = "returns a string"
  value       = aws_route53_record.this.fqdn
}

output "id" {
  description = "returns a string"
  value       = aws_route53_record.this.id
}

output "this" {
  value = aws_route53_record.this
}
```

[top](#index)