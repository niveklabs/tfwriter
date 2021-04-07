# alicloud_sag_dnat_entry

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
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_sag_dnat_entry" {
  source = "./modules/alicloud/r/alicloud_sag_dnat_entry"

  # external_ip - (optional) is a type of string
  external_ip = null
  # external_port - (required) is a type of string
  external_port = null
  # internal_ip - (required) is a type of string
  internal_ip = null
  # internal_port - (required) is a type of string
  internal_port = null
  # ip_protocol - (required) is a type of string
  ip_protocol = null
  # sag_id - (required) is a type of string
  sag_id = null
  # type - (required) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "external_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "external_port" {
  description = "(required)"
  type        = string
}

variable "internal_ip" {
  description = "(required)"
  type        = string
}

variable "internal_port" {
  description = "(required)"
  type        = string
}

variable "ip_protocol" {
  description = "(required)"
  type        = string
}

variable "sag_id" {
  description = "(required)"
  type        = string
}

variable "type" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_sag_dnat_entry" "this" {
  # external_ip - (optional) is a type of string
  external_ip = var.external_ip
  # external_port - (required) is a type of string
  external_port = var.external_port
  # internal_ip - (required) is a type of string
  internal_ip = var.internal_ip
  # internal_port - (required) is a type of string
  internal_port = var.internal_port
  # ip_protocol - (required) is a type of string
  ip_protocol = var.ip_protocol
  # sag_id - (required) is a type of string
  sag_id = var.sag_id
  # type - (required) is a type of string
  type = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_sag_dnat_entry.this.id
}

output "this" {
  value = alicloud_sag_dnat_entry.this
}
```

[top](#index)