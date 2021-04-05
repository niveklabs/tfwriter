# alicloud_alikafka_sasl_users

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
module "alicloud_alikafka_sasl_users" {
  source = "./modules/alicloud/d/alicloud_alikafka_sasl_users"

  # instance_id - (required) is a type of string
  instance_id = null
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "instance_id" {
  description = "(required)"
  type        = string
}

variable "name_regex" {
  description = "(optional)"
  type        = string
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
data "alicloud_alikafka_sasl_users" "this" {
  instance_id = var.instance_id
  name_regex  = var.name_regex
  output_file = var.output_file
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_alikafka_sasl_users.this.id
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_alikafka_sasl_users.this.names
}

output "users" {
  description = "returns a list of object"
  value       = data.alicloud_alikafka_sasl_users.this.users
}

output "this" {
  value = alicloud_alikafka_sasl_users.this
}
```

[top](#index)