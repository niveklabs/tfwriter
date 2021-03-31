# alicloud_cloud_storage_gateway_storage_bundle

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
module "alicloud_cloud_storage_gateway_storage_bundle" {
  source = "./modules/alicloud/r/alicloud_cloud_storage_gateway_storage_bundle"

  # description - (optional) is a type of string
  description = null
  # storage_bundle_name - (required) is a type of string
  storage_bundle_name = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "storage_bundle_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_cloud_storage_gateway_storage_bundle" "this" {
  description         = var.description
  storage_bundle_name = var.storage_bundle_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_cloud_storage_gateway_storage_bundle.this.id
}

output "this" {
  value = alicloud_cloud_storage_gateway_storage_bundle.this
}
```

[top](#index)