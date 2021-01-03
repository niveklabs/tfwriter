# alicloud_ddosbgp_instance

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
module "alicloud_ddosbgp_instance" {
  source = "./modules/alicloud/r/alicloud_ddosbgp_instance"

  # bandwidth - (required) is a type of number
  bandwidth = null
  # base_bandwidth - (optional) is a type of number
  base_bandwidth = null
  # ip_count - (required) is a type of number
  ip_count = null
  # ip_type - (required) is a type of string
  ip_type = null
  # name - (optional) is a type of string
  name = null
  # period - (optional) is a type of number
  period = null
  # type - (optional) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "bandwidth" {
  description = "(required)"
  type        = number
}

variable "base_bandwidth" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ip_count" {
  description = "(required)"
  type        = number
}

variable "ip_type" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_ddosbgp_instance" "this" {
  bandwidth      = var.bandwidth
  base_bandwidth = var.base_bandwidth
  ip_count       = var.ip_count
  ip_type        = var.ip_type
  name           = var.name
  period         = var.period
  type           = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_ddosbgp_instance.this.id
}

output "this" {
  value = alicloud_ddosbgp_instance.this
}
```

[top](#index)