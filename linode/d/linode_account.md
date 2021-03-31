# linode_account

[back](../linode.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    linode = ">= 1.16.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "linode_account" {
  source = "./modules/linode/d/linode_account"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "linode_account" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "address_1" {
  description = "returns a string"
  value       = data.linode_account.this.address_1
}

output "address_2" {
  description = "returns a string"
  value       = data.linode_account.this.address_2
}

output "balance" {
  description = "returns a number"
  value       = data.linode_account.this.balance
}

output "city" {
  description = "returns a string"
  value       = data.linode_account.this.city
}

output "company" {
  description = "returns a string"
  value       = data.linode_account.this.company
}

output "country" {
  description = "returns a string"
  value       = data.linode_account.this.country
}

output "email" {
  description = "returns a string"
  value       = data.linode_account.this.email
}

output "first_name" {
  description = "returns a string"
  value       = data.linode_account.this.first_name
}

output "id" {
  description = "returns a string"
  value       = data.linode_account.this.id
}

output "last_name" {
  description = "returns a string"
  value       = data.linode_account.this.last_name
}

output "phone" {
  description = "returns a string"
  value       = data.linode_account.this.phone
}

output "state" {
  description = "returns a string"
  value       = data.linode_account.this.state
}

output "zip" {
  description = "returns a string"
  value       = data.linode_account.this.zip
}

output "this" {
  value = linode_account.this
}
```

[top](#index)