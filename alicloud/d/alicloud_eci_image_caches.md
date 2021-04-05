# alicloud_eci_image_caches

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
module "alicloud_eci_image_caches" {
  source = "./modules/alicloud/d/alicloud_eci_image_caches"

  # ids - (optional) is a type of list of string
  ids = []
  # image - (optional) is a type of string
  image = null
  # image_cache_name - (optional) is a type of string
  image_cache_name = null
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # snapshot_id - (optional) is a type of string
  snapshot_id = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "image" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "image_cache_name" {
  description = "(optional)"
  type        = string
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

variable "snapshot_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_eci_image_caches" "this" {
  ids              = var.ids
  image            = var.image
  image_cache_name = var.image_cache_name
  name_regex       = var.name_regex
  output_file      = var.output_file
  snapshot_id      = var.snapshot_id
  status           = var.status
}
```

[top](#index)

### Outputs

```terraform
output "caches" {
  description = "returns a list of object"
  value       = data.alicloud_eci_image_caches.this.caches
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_eci_image_caches.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_eci_image_caches.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_eci_image_caches.this.names
}

output "this" {
  value = alicloud_eci_image_caches.this
}
```

[top](#index)