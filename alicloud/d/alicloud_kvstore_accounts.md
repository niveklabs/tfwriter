# alicloud_kvstore_accounts

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
module "alicloud_kvstore_accounts" {
  source = "./modules/alicloud/d/alicloud_kvstore_accounts"

  # account_name - (optional) is a type of string
  account_name = null
  # instance_id - (required) is a type of string
  instance_id = null
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "account_name" {
  description = "(optional)"
  type        = string
  default     = null
}

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

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_kvstore_accounts" "this" {
  account_name = var.account_name
  instance_id  = var.instance_id
  name_regex   = var.name_regex
  output_file  = var.output_file
  status       = var.status
}
```

[top](#index)

### Outputs

```terraform
output "accounts" {
  description = "returns a list of object"
  value       = data.alicloud_kvstore_accounts.this.accounts
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_kvstore_accounts.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_kvstore_accounts.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_kvstore_accounts.this.names
}

output "this" {
  value = alicloud_kvstore_accounts.this
}
```

[top](#index)