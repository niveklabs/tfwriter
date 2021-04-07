# alicloud_nas_protocols

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
module "alicloud_nas_protocols" {
  source = "./modules/alicloud/d/alicloud_nas_protocols"

  # output_file - (optional) is a type of string
  output_file = null
  # type - (required) is a type of string
  type = null
  # zone_id - (optional) is a type of string
  zone_id = null
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

variable "type" {
  description = "(required)"
  type        = string
}

variable "zone_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_nas_protocols" "this" {
  # output_file - (optional) is a type of string
  output_file = var.output_file
  # type - (required) is a type of string
  type = var.type
  # zone_id - (optional) is a type of string
  zone_id = var.zone_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_nas_protocols.this.id
}

output "protocols" {
  description = "returns a list of string"
  value       = data.alicloud_nas_protocols.this.protocols
}

output "this" {
  value = alicloud_nas_protocols.this
}
```

[top](#index)