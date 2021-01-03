# alicloud_alikafka_instance

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
module "alicloud_alikafka_instance" {
  source = "./modules/alicloud/r/alicloud_alikafka_instance"

  # deploy_type - (required) is a type of number
  deploy_type = null
  # disk_size - (required) is a type of number
  disk_size = null
  # disk_type - (required) is a type of number
  disk_type = null
  # eip_max - (optional) is a type of number
  eip_max = null
  # io_max - (required) is a type of number
  io_max = null
  # name - (optional) is a type of string
  name = null
  # paid_type - (optional) is a type of string
  paid_type = null
  # security_group - (optional) is a type of string
  security_group = null
  # spec_type - (optional) is a type of string
  spec_type = null
  # tags - (optional) is a type of map of string
  tags = {}
  # topic_quota - (required) is a type of number
  topic_quota = null
  # vswitch_id - (required) is a type of string
  vswitch_id = null
}
```

[top](#index)

### Variables

```terraform
variable "deploy_type" {
  description = "(required)"
  type        = number
}

variable "disk_size" {
  description = "(required)"
  type        = number
}

variable "disk_type" {
  description = "(required)"
  type        = number
}

variable "eip_max" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "io_max" {
  description = "(required)"
  type        = number
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "paid_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "spec_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "topic_quota" {
  description = "(required)"
  type        = number
}

variable "vswitch_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_alikafka_instance" "this" {
  deploy_type    = var.deploy_type
  disk_size      = var.disk_size
  disk_type      = var.disk_type
  eip_max        = var.eip_max
  io_max         = var.io_max
  name           = var.name
  paid_type      = var.paid_type
  security_group = var.security_group
  spec_type      = var.spec_type
  tags           = var.tags
  topic_quota    = var.topic_quota
  vswitch_id     = var.vswitch_id
}
```

[top](#index)

### Outputs

```terraform
output "end_point" {
  description = "returns a string"
  value       = alicloud_alikafka_instance.this.end_point
}

output "id" {
  description = "returns a string"
  value       = alicloud_alikafka_instance.this.id
}

output "name" {
  description = "returns a string"
  value       = alicloud_alikafka_instance.this.name
}

output "vpc_id" {
  description = "returns a string"
  value       = alicloud_alikafka_instance.this.vpc_id
}

output "zone_id" {
  description = "returns a string"
  value       = alicloud_alikafka_instance.this.zone_id
}

output "this" {
  value = alicloud_alikafka_instance.this
}
```

[top](#index)