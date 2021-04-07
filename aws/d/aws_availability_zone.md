# aws_availability_zone

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "aws_availability_zone" {
  source = "./modules/aws/d/aws_availability_zone"

  # all_availability_zones - (optional) is a type of bool
  all_availability_zones = null
  # name - (optional) is a type of string
  name = null
  # state - (optional) is a type of string
  state = null
  # zone_id - (optional) is a type of string
  zone_id = null

  filter = [{
    name   = null
    values = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "all_availability_zones" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "zone_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "filter" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name   = string
      values = set(string)
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "aws_availability_zone" "this" {
  # all_availability_zones - (optional) is a type of bool
  all_availability_zones = var.all_availability_zones
  # name - (optional) is a type of string
  name = var.name
  # state - (optional) is a type of string
  state = var.state
  # zone_id - (optional) is a type of string
  zone_id = var.zone_id

  dynamic "filter" {
    for_each = var.filter
    content {
      # name - (required) is a type of string
      name = filter.value["name"]
      # values - (required) is a type of set of string
      values = filter.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "group_name" {
  description = "returns a string"
  value       = data.aws_availability_zone.this.group_name
}

output "id" {
  description = "returns a string"
  value       = data.aws_availability_zone.this.id
}

output "name" {
  description = "returns a string"
  value       = data.aws_availability_zone.this.name
}

output "name_suffix" {
  description = "returns a string"
  value       = data.aws_availability_zone.this.name_suffix
}

output "network_border_group" {
  description = "returns a string"
  value       = data.aws_availability_zone.this.network_border_group
}

output "opt_in_status" {
  description = "returns a string"
  value       = data.aws_availability_zone.this.opt_in_status
}

output "parent_zone_id" {
  description = "returns a string"
  value       = data.aws_availability_zone.this.parent_zone_id
}

output "parent_zone_name" {
  description = "returns a string"
  value       = data.aws_availability_zone.this.parent_zone_name
}

output "region" {
  description = "returns a string"
  value       = data.aws_availability_zone.this.region
}

output "state" {
  description = "returns a string"
  value       = data.aws_availability_zone.this.state
}

output "zone_id" {
  description = "returns a string"
  value       = data.aws_availability_zone.this.zone_id
}

output "zone_type" {
  description = "returns a string"
  value       = data.aws_availability_zone.this.zone_type
}

output "this" {
  value = aws_availability_zone.this
}
```

[top](#index)