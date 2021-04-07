# alicloud_ram_account_alias

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
module "alicloud_ram_account_alias" {
  source = "./modules/alicloud/r/alicloud_ram_account_alias"

  # account_alias - (required) is a type of string
  account_alias = null
}
```

[top](#index)

### Variables

```terraform
variable "account_alias" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_ram_account_alias" "this" {
  # account_alias - (required) is a type of string
  account_alias = var.account_alias
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_ram_account_alias.this.id
}

output "this" {
  value = alicloud_ram_account_alias.this
}
```

[top](#index)