# akamai_iam_contact_types

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
module "akamai_iam_contact_types" {
  source = "./modules/akamai/d/akamai_iam_contact_types"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "akamai_iam_contact_types" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "contact_types" {
  description = "returns a set of string"
  value       = data.akamai_iam_contact_types.this.contact_types
}

output "id" {
  description = "returns a string"
  value       = data.akamai_iam_contact_types.this.id
}

output "this" {
  value = akamai_iam_contact_types.this
}
```

[top](#index)