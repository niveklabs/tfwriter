# alicloud_dns_record

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
module "alicloud_dns_record" {
  source = "./modules/alicloud/r/alicloud_dns_record"

  # host_record - (required) is a type of string
  host_record = null
  # name - (required) is a type of string
  name = null
  # priority - (optional) is a type of number
  priority = null
  # routing - (optional) is a type of string
  routing = null
  # ttl - (optional) is a type of number
  ttl = null
  # type - (required) is a type of string
  type = null
  # value - (required) is a type of string
  value = null
}
```

[top](#index)

### Variables

```terraform
variable "host_record" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "priority" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "routing" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "value" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_dns_record" "this" {
  host_record = var.host_record
  name        = var.name
  priority    = var.priority
  routing     = var.routing
  ttl         = var.ttl
  type        = var.type
  value       = var.value
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_dns_record.this.id
}

output "locked" {
  description = "returns a bool"
  value       = alicloud_dns_record.this.locked
}

output "status" {
  description = "returns a string"
  value       = alicloud_dns_record.this.status
}

output "this" {
  value = alicloud_dns_record.this
}
```

[top](#index)