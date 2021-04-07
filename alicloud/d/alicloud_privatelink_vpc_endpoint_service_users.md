# alicloud_privatelink_vpc_endpoint_service_users

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_privatelink_vpc_endpoint_service_users" {
  source = "./modules/alicloud/d/alicloud_privatelink_vpc_endpoint_service_users"

  # output_file - (optional) is a type of string
  output_file = null
  # service_id - (required) is a type of string
  service_id = null
  # user_id - (optional) is a type of string
  user_id = null
}
```

[top](#index)

### Variables

```terraform
variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_id" {
  description = "(required)"
  type        = string
}

variable "user_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_privatelink_vpc_endpoint_service_users" "this" {
  # output_file - (optional) is a type of string
  output_file = var.output_file
  # service_id - (required) is a type of string
  service_id = var.service_id
  # user_id - (optional) is a type of string
  user_id = var.user_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_privatelink_vpc_endpoint_service_users.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_privatelink_vpc_endpoint_service_users.this.ids
}

output "users" {
  description = "returns a list of object"
  value       = data.alicloud_privatelink_vpc_endpoint_service_users.this.users
}

output "this" {
  value = alicloud_privatelink_vpc_endpoint_service_users.this
}
```

[top](#index)