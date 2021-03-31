# alicloud_cdn_service

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
module "alicloud_cdn_service" {
  source = "./modules/alicloud/d/alicloud_cdn_service"

  # enable - (optional) is a type of string
  enable = null
  # internet_charge_type - (optional) is a type of string
  internet_charge_type = null
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

variable "internet_charge_type" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_cdn_service" "this" {
  enable               = var.enable
  internet_charge_type = var.internet_charge_type
}
```

[top](#index)

### Outputs

```terraform
output "changing_affect_time" {
  description = "returns a string"
  value       = data.alicloud_cdn_service.this.changing_affect_time
}

output "changing_charge_type" {
  description = "returns a string"
  value       = data.alicloud_cdn_service.this.changing_charge_type
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_cdn_service.this.id
}

output "opening_time" {
  description = "returns a string"
  value       = data.alicloud_cdn_service.this.opening_time
}

output "status" {
  description = "returns a string"
  value       = data.alicloud_cdn_service.this.status
}

output "this" {
  value = alicloud_cdn_service.this
}
```

[top](#index)