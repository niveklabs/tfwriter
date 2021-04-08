# vultr_account

[back](../vultr.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vultr = ">= 2.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vultr_account" {
  source = "./modules/vultr/d/vultr_account"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "vultr_account" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "acl" {
  description = "returns a list of string"
  value       = data.vultr_account.this.acl
}

output "balance" {
  description = "returns a number"
  value       = data.vultr_account.this.balance
}

output "email" {
  description = "returns a string"
  value       = data.vultr_account.this.email
}

output "id" {
  description = "returns a string"
  value       = data.vultr_account.this.id
}

output "last_payment_amount" {
  description = "returns a number"
  value       = data.vultr_account.this.last_payment_amount
}

output "last_payment_date" {
  description = "returns a string"
  value       = data.vultr_account.this.last_payment_date
}

output "name" {
  description = "returns a string"
  value       = data.vultr_account.this.name
}

output "pending_charges" {
  description = "returns a number"
  value       = data.vultr_account.this.pending_charges
}

output "this" {
  value = vultr_account.this
}
```

[top](#index)