# alicloud_ram_account_alias

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
module "alicloud_ram_account_alias" {
  source = "./modules/alicloud/d/alicloud_ram_account_alias"

  # output_file - (optional) is a type of string
  output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_ram_account_alias" "this" {
  output_file = var.output_file
}
```

[top](#index)

### Outputs

```terraform
output "account_alias" {
  description = "returns a string"
  value       = data.alicloud_ram_account_alias.this.account_alias
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_ram_account_alias.this.id
}

output "this" {
  value = alicloud_ram_account_alias.this
}
```

[top](#index)