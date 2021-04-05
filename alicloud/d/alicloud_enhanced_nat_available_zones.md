# alicloud_enhanced_nat_available_zones

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
module "alicloud_enhanced_nat_available_zones" {
  source = "./modules/alicloud/d/alicloud_enhanced_nat_available_zones"

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
data "alicloud_enhanced_nat_available_zones" "this" {
  output_file = var.output_file
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_enhanced_nat_available_zones.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_enhanced_nat_available_zones.this.ids
}

output "zones" {
  description = "returns a list of object"
  value       = data.alicloud_enhanced_nat_available_zones.this.zones
}

output "this" {
  value = alicloud_enhanced_nat_available_zones.this
}
```

[top](#index)