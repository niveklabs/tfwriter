# alicloud_privatelink_vpc_endpoint_service_user

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
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_privatelink_vpc_endpoint_service_user" {
  source = "./modules/alicloud/r/alicloud_privatelink_vpc_endpoint_service_user"

  # dry_run - (optional) is a type of bool
  dry_run = null
  # service_id - (required) is a type of string
  service_id = null
  # user_id - (required) is a type of string
  user_id = null
}
```

[top](#index)

### Variables

```terraform
variable "dry_run" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "service_id" {
  description = "(required)"
  type        = string
}

variable "user_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_privatelink_vpc_endpoint_service_user" "this" {
  # dry_run - (optional) is a type of bool
  dry_run = var.dry_run
  # service_id - (required) is a type of string
  service_id = var.service_id
  # user_id - (required) is a type of string
  user_id = var.user_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_privatelink_vpc_endpoint_service_user.this.id
}

output "this" {
  value = alicloud_privatelink_vpc_endpoint_service_user.this
}
```

[top](#index)