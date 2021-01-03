# okta_everyone_group

[back](../okta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    okta = ">= 3.7.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "okta_everyone_group" {
  source = "./modules/okta/d/okta_everyone_group"

  # include_users - (optional) is a type of bool
  include_users = null
}
```

[top](#index)

### Variables

```terraform
variable "include_users" {
  description = "(optional) - Fetch group users, having default off cuts down on API calls."
  type        = bool
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "okta_everyone_group" "this" {
  include_users = var.include_users
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.okta_everyone_group.this.description
}

output "id" {
  description = "returns a string"
  value       = data.okta_everyone_group.this.id
}

output "this" {
  value = okta_everyone_group.this
}
```

[top](#index)