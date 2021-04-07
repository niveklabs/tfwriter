# newrelic_key_transaction

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
    newrelic = ">= 2.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "newrelic_key_transaction" {
  source = "./modules/newrelic/d/newrelic_key_transaction"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - The name of the key transaction in New Relic."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "newrelic_key_transaction" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.newrelic_key_transaction.this.id
}

output "this" {
  value = newrelic_key_transaction.this
}
```

[top](#index)