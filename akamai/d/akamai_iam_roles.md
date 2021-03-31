# akamai_iam_roles

[back](../akamai.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    akamai = ">= 1.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "akamai_iam_roles" {
  source = "./modules/akamai/d/akamai_iam_roles"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "akamai_iam_roles" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.akamai_iam_roles.this.id
}

output "roles" {
  description = "returns a set of object"
  value       = data.akamai_iam_roles.this.roles
}

output "this" {
  value = akamai_iam_roles.this
}
```

[top](#index)