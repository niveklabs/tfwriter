# alicloud_havip

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
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_havip" {
  source = "./modules/alicloud/r/alicloud_havip"

  # description - (optional) is a type of string
  description = null
  # ip_address - (optional) is a type of string
  ip_address = null
  # vswitch_id - (required) is a type of string
  vswitch_id = null
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

variable "ip_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vswitch_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_havip" "this" {
  description = var.description
  ip_address  = var.ip_address
  vswitch_id  = var.vswitch_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_havip.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = alicloud_havip.this.ip_address
}

output "this" {
  value = alicloud_havip.this
}
```

[top](#index)