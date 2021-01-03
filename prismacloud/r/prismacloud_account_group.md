# prismacloud_account_group

[back](../prismacloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    prismacloud = ">= 1.0.8"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "prismacloud_account_group" {
  source = "./modules/prismacloud/r/prismacloud_account_group"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name of the group"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "prismacloud_account_group" "this" {
  description = var.description
  name        = var.name
}
```

[top](#index)

### Outputs

```terraform
output "account_ids" {
  description = "returns a list of string"
  value       = prismacloud_account_group.this.account_ids
}

output "group_id" {
  description = "returns a string"
  value       = prismacloud_account_group.this.group_id
}

output "id" {
  description = "returns a string"
  value       = prismacloud_account_group.this.id
}

output "last_modified_by" {
  description = "returns a string"
  value       = prismacloud_account_group.this.last_modified_by
}

output "last_modified_ts" {
  description = "returns a number"
  value       = prismacloud_account_group.this.last_modified_ts
}

output "this" {
  value = prismacloud_account_group.this
}
```

[top](#index)