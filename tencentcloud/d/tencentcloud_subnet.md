# tencentcloud_subnet

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
module "tencentcloud_subnet" {
  source = "./modules/tencentcloud/d/tencentcloud_subnet"

  # subnet_id - (required) is a type of string
  subnet_id = null
  # vpc_id - (required) is a type of string
  vpc_id = null
}
```

[top](#index)

### Variables

```terraform
variable "subnet_id" {
  description = "(required) - The ID of the Subnet."
  type        = string
}

variable "vpc_id" {
  description = "(required) - The VPC ID."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_subnet" "this" {
  # subnet_id - (required) is a type of string
  subnet_id = var.subnet_id
  # vpc_id - (required) is a type of string
  vpc_id = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "availability_zone" {
  description = "returns a string"
  value       = data.tencentcloud_subnet.this.availability_zone
}

output "cidr_block" {
  description = "returns a string"
  value       = data.tencentcloud_subnet.this.cidr_block
}

output "id" {
  description = "returns a string"
  value       = data.tencentcloud_subnet.this.id
}

output "name" {
  description = "returns a string"
  value       = data.tencentcloud_subnet.this.name
}

output "route_table_id" {
  description = "returns a string"
  value       = data.tencentcloud_subnet.this.route_table_id
}

output "this" {
  value = tencentcloud_subnet.this
}
```

[top](#index)