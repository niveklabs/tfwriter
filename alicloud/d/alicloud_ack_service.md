# alicloud_ack_service

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
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_ack_service" {
  source = "./modules/alicloud/d/alicloud_ack_service"

  # enable - (optional) is a type of string
  enable = null
  # type - (required) is a type of string
  type = null
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

variable "type" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_ack_service" "this" {
  enable = var.enable
  type   = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_ack_service.this.id
}

output "status" {
  description = "returns a string"
  value       = data.alicloud_ack_service.this.status
}

output "this" {
  value = alicloud_ack_service.this
}
```

[top](#index)