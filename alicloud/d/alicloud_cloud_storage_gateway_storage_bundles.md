# alicloud_cloud_storage_gateway_storage_bundles

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
module "alicloud_cloud_storage_gateway_storage_bundles" {
  source = "./modules/alicloud/d/alicloud_cloud_storage_gateway_storage_bundles"

  # backend_bucket_region_id - (required) is a type of string
  backend_bucket_region_id = null
  # ids - (optional) is a type of list of string
  ids = []
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "backend_bucket_region_id" {
  description = "(required)"
  type        = string
}

variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "name_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_cloud_storage_gateway_storage_bundles" "this" {
  # backend_bucket_region_id - (required) is a type of string
  backend_bucket_region_id = var.backend_bucket_region_id
  # ids - (optional) is a type of list of string
  ids = var.ids
  # name_regex - (optional) is a type of string
  name_regex = var.name_regex
  # output_file - (optional) is a type of string
  output_file = var.output_file
}
```

[top](#index)

### Outputs

```terraform
output "bundles" {
  description = "returns a list of object"
  value       = data.alicloud_cloud_storage_gateway_storage_bundles.this.bundles
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_cloud_storage_gateway_storage_bundles.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_cloud_storage_gateway_storage_bundles.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_cloud_storage_gateway_storage_bundles.this.names
}

output "this" {
  value = alicloud_cloud_storage_gateway_storage_bundles.this
}
```

[top](#index)