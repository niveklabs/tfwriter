# alicloud_ddoscoo_instance

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
module "alicloud_ddoscoo_instance" {
  source = "./modules/alicloud/r/alicloud_ddoscoo_instance"

  # bandwidth - (required) is a type of string
  bandwidth = null
  # base_bandwidth - (required) is a type of string
  base_bandwidth = null
  # domain_count - (required) is a type of string
  domain_count = null
  # name - (required) is a type of string
  name = null
  # period - (optional) is a type of number
  period = null
  # port_count - (required) is a type of string
  port_count = null
  # service_bandwidth - (required) is a type of string
  service_bandwidth = null
}
```

[top](#index)

### Variables

```terraform
variable "bandwidth" {
  description = "(required)"
  type        = string
}

variable "base_bandwidth" {
  description = "(required)"
  type        = string
}

variable "domain_count" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "port_count" {
  description = "(required)"
  type        = string
}

variable "service_bandwidth" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_ddoscoo_instance" "this" {
  # bandwidth - (required) is a type of string
  bandwidth = var.bandwidth
  # base_bandwidth - (required) is a type of string
  base_bandwidth = var.base_bandwidth
  # domain_count - (required) is a type of string
  domain_count = var.domain_count
  # name - (required) is a type of string
  name = var.name
  # period - (optional) is a type of number
  period = var.period
  # port_count - (required) is a type of string
  port_count = var.port_count
  # service_bandwidth - (required) is a type of string
  service_bandwidth = var.service_bandwidth
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_ddoscoo_instance.this.id
}

output "this" {
  value = alicloud_ddoscoo_instance.this
}
```

[top](#index)