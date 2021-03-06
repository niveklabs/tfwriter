# alicloud_kms_service

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
module "alicloud_kms_service" {
  source = "./modules/alicloud/d/alicloud_kms_service"

  # enable - (optional) is a type of string
  enable = null
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
```

[top](#index)

### Datasource

```terraform
data "alicloud_kms_service" "this" {
  # enable - (optional) is a type of string
  enable = var.enable
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_kms_service.this.id
}

output "status" {
  description = "returns a string"
  value       = data.alicloud_kms_service.this.status
}

output "this" {
  value = alicloud_kms_service.this
}
```

[top](#index)