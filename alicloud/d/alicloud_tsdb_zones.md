# alicloud_tsdb_zones

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
module "alicloud_tsdb_zones" {
  source = "./modules/alicloud/d/alicloud_tsdb_zones"

  # output_file - (optional) is a type of string
  output_file = null
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
```

[top](#index)

### Datasource

```terraform
data "alicloud_tsdb_zones" "this" {
  output_file = var.output_file
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_tsdb_zones.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_tsdb_zones.this.ids
}

output "zones" {
  description = "returns a list of object"
  value       = data.alicloud_tsdb_zones.this.zones
}

output "this" {
  value = alicloud_tsdb_zones.this
}
```

[top](#index)