# prismacloud_account_group

[back](../prismacloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    prismacloud = ">= 1.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "prismacloud_account_group" {
  source = "./modules/prismacloud/d/prismacloud_account_group"

  # group_id - (optional) is a type of string
  group_id = null
  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "group_id" {
  description = "(optional) - Account group ID"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - Name of the group"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "prismacloud_account_group" "this" {
  group_id = var.group_id
  name     = var.name
}
```

[top](#index)

### Outputs

```terraform
output "account_ids" {
  description = "returns a list of string"
  value       = data.prismacloud_account_group.this.account_ids
}

output "description" {
  description = "returns a string"
  value       = data.prismacloud_account_group.this.description
}

output "group_id" {
  description = "returns a string"
  value       = data.prismacloud_account_group.this.group_id
}

output "id" {
  description = "returns a string"
  value       = data.prismacloud_account_group.this.id
}

output "last_modified_by" {
  description = "returns a string"
  value       = data.prismacloud_account_group.this.last_modified_by
}

output "last_modified_ts" {
  description = "returns a number"
  value       = data.prismacloud_account_group.this.last_modified_ts
}

output "name" {
  description = "returns a string"
  value       = data.prismacloud_account_group.this.name
}

output "this" {
  value = prismacloud_account_group.this
}
```

[top](#index)