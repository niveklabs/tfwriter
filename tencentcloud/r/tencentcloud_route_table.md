# tencentcloud_route_table

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
module "tencentcloud_route_table" {
  source = "./modules/tencentcloud/r/tencentcloud_route_table"

  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vpc_id - (required) is a type of string
  vpc_id = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - The name of routing table."
  type        = string
}

variable "tags" {
  description = "(optional) - The tags of routing table."
  type        = map(string)
  default     = null
}

variable "vpc_id" {
  description = "(required) - ID of VPC to which the route table should be associated."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_route_table" "this" {
  name   = var.name
  tags   = var.tags
  vpc_id = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = tencentcloud_route_table.this.create_time
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_route_table.this.id
}

output "is_default" {
  description = "returns a bool"
  value       = tencentcloud_route_table.this.is_default
}

output "route_entry_ids" {
  description = "returns a list of string"
  value       = tencentcloud_route_table.this.route_entry_ids
}

output "subnet_ids" {
  description = "returns a list of string"
  value       = tencentcloud_route_table.this.subnet_ids
}

output "this" {
  value = tencentcloud_route_table.this
}
```

[top](#index)