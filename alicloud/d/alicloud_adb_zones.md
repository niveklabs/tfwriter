# alicloud_adb_zones

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
module "alicloud_adb_zones" {
  source = "./modules/alicloud/d/alicloud_adb_zones"

  # multi - (optional) is a type of bool
  multi = null
  # output_file - (optional) is a type of string
  output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "multi" {
  description = "(optional)"
  type        = bool
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
data "alicloud_adb_zones" "this" {
  # multi - (optional) is a type of bool
  multi = var.multi
  # output_file - (optional) is a type of string
  output_file = var.output_file
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_adb_zones.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_adb_zones.this.ids
}

output "zones" {
  description = "returns a list of object"
  value       = data.alicloud_adb_zones.this.zones
}

output "this" {
  value = alicloud_adb_zones.this
}
```

[top](#index)