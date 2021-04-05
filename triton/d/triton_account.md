# triton_account

[back](../triton.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    triton = ">= 0.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "triton_account" {
  source = "./modules/triton/d/triton_account"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "triton_account" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "cns_enabled" {
  description = "returns a bool"
  value       = data.triton_account.this.cns_enabled
}

output "email" {
  description = "returns a string"
  value       = data.triton_account.this.email
}

output "id" {
  description = "returns a string"
  value       = data.triton_account.this.id
}

output "login" {
  description = "returns a string"
  value       = data.triton_account.this.login
}

output "this" {
  value = triton_account.this
}
```

[top](#index)