# newrelic_account

[back](../newrelic.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    newrelic = ">= 2.14.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "newrelic_account" {
  source = "./modules/newrelic/d/newrelic_account"

  # account_id - (optional) is a type of number
  account_id = null
  # name - (optional) is a type of string
  name = null
  # scope - (optional) is a type of string
  scope = null
}
```

[top](#index)

### Variables

```terraform
variable "account_id" {
  description = "(optional) - The ID of the account in New Relic."
  type        = number
  default     = null
}

variable "name" {
  description = "(optional) - The name of the account in New Relic."
  type        = string
  default     = null
}

variable "scope" {
  description = "(optional) - The scope of the account in New Relic.  Valid values are \"global\" and \"in_region\".  Defaults to \"in_region\"."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "newrelic_account" "this" {
  account_id = var.account_id
  name       = var.name
  scope      = var.scope
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.newrelic_account.this.id
}

output "this" {
  value = newrelic_account.this
}
```

[top](#index)