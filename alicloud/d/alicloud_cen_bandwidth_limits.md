# alicloud_cen_bandwidth_limits

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
module "alicloud_cen_bandwidth_limits" {
  source = "./modules/alicloud/d/alicloud_cen_bandwidth_limits"

  # instance_ids - (optional) is a type of list of string
  instance_ids = []
  # output_file - (optional) is a type of string
  output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "instance_ids" {
  description = "(optional)"
  type        = list(string)
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
data "alicloud_cen_bandwidth_limits" "this" {
  # instance_ids - (optional) is a type of list of string
  instance_ids = var.instance_ids
  # output_file - (optional) is a type of string
  output_file = var.output_file
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_cen_bandwidth_limits.this.id
}

output "limits" {
  description = "returns a list of object"
  value       = data.alicloud_cen_bandwidth_limits.this.limits
}

output "this" {
  value = alicloud_cen_bandwidth_limits.this
}
```

[top](#index)