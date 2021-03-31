# alicloud_privatelink_vpc_endpoint_zones

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
module "alicloud_privatelink_vpc_endpoint_zones" {
  source = "./modules/alicloud/d/alicloud_privatelink_vpc_endpoint_zones"

  # endpoint_id - (required) is a type of string
  endpoint_id = null
  # output_file - (optional) is a type of string
  output_file = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "endpoint_id" {
  description = "(required)"
  type        = string
}

variable "output_file" {
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
data "alicloud_privatelink_vpc_endpoint_zones" "this" {
  endpoint_id = var.endpoint_id
  output_file = var.output_file
  status      = var.status
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_privatelink_vpc_endpoint_zones.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_privatelink_vpc_endpoint_zones.this.ids
}

output "zones" {
  description = "returns a list of object"
  value       = data.alicloud_privatelink_vpc_endpoint_zones.this.zones
}

output "this" {
  value = alicloud_privatelink_vpc_endpoint_zones.this
}
```

[top](#index)