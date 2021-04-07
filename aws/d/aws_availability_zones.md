# aws_availability_zones

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
module "aws_availability_zones" {
  source = "./modules/aws/d/aws_availability_zones"

  # all_availability_zones - (optional) is a type of bool
  all_availability_zones = null
  # exclude_names - (optional) is a type of set of string
  exclude_names = []
  # exclude_zone_ids - (optional) is a type of set of string
  exclude_zone_ids = []
  # state - (optional) is a type of string
  state = null

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

variable "exclude_names" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "exclude_zone_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "state" {
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
data "aws_availability_zones" "this" {
  # all_availability_zones - (optional) is a type of bool
  all_availability_zones = var.all_availability_zones
  # exclude_names - (optional) is a type of set of string
  exclude_names = var.exclude_names
  # exclude_zone_ids - (optional) is a type of set of string
  exclude_zone_ids = var.exclude_zone_ids
  # state - (optional) is a type of string
  state = var.state

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
output "group_names" {
  description = "returns a set of string"
  value       = data.aws_availability_zones.this.group_names
}

output "id" {
  description = "returns a string"
  value       = data.aws_availability_zones.this.id
}

output "names" {
  description = "returns a list of string"
  value       = data.aws_availability_zones.this.names
}

output "zone_ids" {
  description = "returns a list of string"
  value       = data.aws_availability_zones.this.zone_ids
}

output "this" {
  value = aws_availability_zones.this
}
```

[top](#index)