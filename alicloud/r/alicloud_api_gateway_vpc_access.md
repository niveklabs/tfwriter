# alicloud_api_gateway_vpc_access

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_api_gateway_vpc_access" {
  source = "./modules/alicloud/r/alicloud_api_gateway_vpc_access"

  # instance_id - (required) is a type of string
  instance_id = null
  # name - (required) is a type of string
  name = null
  # port - (required) is a type of number
  port = null
  # vpc_id - (required) is a type of string
  vpc_id = null
}
```

[top](#index)

### Variables

```terraform
variable "instance_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "port" {
  description = "(required)"
  type        = number
}

variable "vpc_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_api_gateway_vpc_access" "this" {
  instance_id = var.instance_id
  name        = var.name
  port        = var.port
  vpc_id      = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_api_gateway_vpc_access.this.id
}

output "this" {
  value = alicloud_api_gateway_vpc_access.this
}
```

[top](#index)