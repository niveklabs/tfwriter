# tencentcloud_route_table

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/tencentcloud/d/tencentcloud_route_table"

  # name - (optional) is a type of string
  name = null
  # route_table_id - (required) is a type of string
  route_table_id = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - The Route Table name."
  type        = string
  default     = null
}

variable "route_table_id" {
  description = "(required) - The Route Table ID."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_route_table" "this" {
  name           = var.name
  route_table_id = var.route_table_id
}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = data.tencentcloud_route_table.this.create_time
}

output "id" {
  description = "returns a string"
  value       = data.tencentcloud_route_table.this.id
}

output "routes" {
  description = "returns a list of object"
  value       = data.tencentcloud_route_table.this.routes
}

output "subnet_num" {
  description = "returns a number"
  value       = data.tencentcloud_route_table.this.subnet_num
}

output "vpc_id" {
  description = "returns a string"
  value       = data.tencentcloud_route_table.this.vpc_id
}

output "this" {
  value = tencentcloud_route_table.this
}
```

[top](#index)