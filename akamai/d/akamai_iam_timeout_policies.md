# akamai_iam_timeout_policies

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
module "akamai_iam_timeout_policies" {
  source = "./modules/akamai/d/akamai_iam_timeout_policies"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "akamai_iam_timeout_policies" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.akamai_iam_timeout_policies.this.id
}

output "policies" {
  description = "returns a map of number"
  value       = data.akamai_iam_timeout_policies.this.policies
}

output "this" {
  value = akamai_iam_timeout_policies.this
}
```

[top](#index)