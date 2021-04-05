# alicloud_cr_service

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
module "alicloud_cr_service" {
  source = "./modules/alicloud/d/alicloud_cr_service"

  # enable - (optional) is a type of string
  enable = null
  # password - (required) is a type of string
  password = null
}
```

[top](#index)

### Variables

```terraform
variable "enable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "password" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_cr_service" "this" {
  enable   = var.enable
  password = var.password
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_cr_service.this.id
}

output "status" {
  description = "returns a string"
  value       = data.alicloud_cr_service.this.status
}

output "this" {
  value = alicloud_cr_service.this
}
```

[top](#index)