# alicloud_resource_manager_accounts

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
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_resource_manager_accounts" {
  source = "./modules/alicloud/d/alicloud_resource_manager_accounts"

  # ids - (optional) is a type of list of string
  ids = []
  # output_file - (optional) is a type of string
  output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "ids" {
  description = "(optional)"
  type        = list(string)
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
data "alicloud_resource_manager_accounts" "this" {
  ids         = var.ids
  output_file = var.output_file
}
```

[top](#index)

### Outputs

```terraform
output "accounts" {
  description = "returns a list of object"
  value       = data.alicloud_resource_manager_accounts.this.accounts
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_resource_manager_accounts.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_resource_manager_accounts.this.ids
}

output "this" {
  value = alicloud_resource_manager_accounts.this
}
```

[top](#index)