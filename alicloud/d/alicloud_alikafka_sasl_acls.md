# alicloud_alikafka_sasl_acls

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
module "alicloud_alikafka_sasl_acls" {
  source = "./modules/alicloud/d/alicloud_alikafka_sasl_acls"

  # acl_resource_name - (required) is a type of string
  acl_resource_name = null
  # acl_resource_type - (required) is a type of string
  acl_resource_type = null
  # instance_id - (required) is a type of string
  instance_id = null
  # output_file - (optional) is a type of string
  output_file = null
  # username - (required) is a type of string
  username = null
}
```

[top](#index)

### Variables

```terraform
variable "acl_resource_name" {
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

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "username" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_alikafka_sasl_acls" "this" {
  acl_resource_name = var.acl_resource_name
  acl_resource_type = var.acl_resource_type
  instance_id       = var.instance_id
  output_file       = var.output_file
  username          = var.username
}
```

[top](#index)

### Outputs

```terraform
output "acls" {
  description = "returns a list of object"
  value       = data.alicloud_alikafka_sasl_acls.this.acls
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_alikafka_sasl_acls.this.id
}

output "this" {
  value = alicloud_alikafka_sasl_acls.this
}
```

[top](#index)