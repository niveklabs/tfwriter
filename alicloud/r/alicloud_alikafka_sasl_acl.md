# alicloud_alikafka_sasl_acl

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
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_alikafka_sasl_acl" {
  source = "./modules/alicloud/r/alicloud_alikafka_sasl_acl"

  # acl_operation_type - (required) is a type of string
  acl_operation_type = null
  # acl_resource_name - (required) is a type of string
  acl_resource_name = null
  # acl_resource_pattern_type - (required) is a type of string
  acl_resource_pattern_type = null
  # acl_resource_type - (required) is a type of string
  acl_resource_type = null
  # instance_id - (required) is a type of string
  instance_id = null
  # username - (required) is a type of string
  username = null
}
```

[top](#index)

### Variables

```terraform
variable "acl_operation_type" {
  description = "(required)"
  type        = string
}

variable "acl_resource_name" {
  description = "(required)"
  type        = string
}

variable "acl_resource_pattern_type" {
  description = "(required)"
  type        = string
}

variable "acl_resource_type" {
  description = "(required)"
  type        = string
}

variable "instance_id" {
  description = "(required)"
  type        = string
}

variable "username" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_alikafka_sasl_acl" "this" {
  acl_operation_type        = var.acl_operation_type
  acl_resource_name         = var.acl_resource_name
  acl_resource_pattern_type = var.acl_resource_pattern_type
  acl_resource_type         = var.acl_resource_type
  instance_id               = var.instance_id
  username                  = var.username
}
```

[top](#index)

### Outputs

```terraform
output "host" {
  description = "returns a string"
  value       = alicloud_alikafka_sasl_acl.this.host
}

output "id" {
  description = "returns a string"
  value       = alicloud_alikafka_sasl_acl.this.id
}

output "this" {
  value = alicloud_alikafka_sasl_acl.this
}
```

[top](#index)