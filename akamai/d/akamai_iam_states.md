# akamai_iam_states

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
module "akamai_iam_states" {
  source = "./modules/akamai/d/akamai_iam_states"

  # country - (required) is a type of string
  country = null
}
```

[top](#index)

### Variables

```terraform
variable "country" {
  description = "(required) - Specifies a US state or Canadian province"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "akamai_iam_states" "this" {
  # country - (required) is a type of string
  country = var.country
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.akamai_iam_states.this.id
}

output "states" {
  description = "returns a set of string"
  value       = data.akamai_iam_states.this.states
}

output "this" {
  value = akamai_iam_states.this
}
```

[top](#index)