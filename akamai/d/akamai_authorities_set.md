# akamai_authorities_set

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
    akamai = ">= 1.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "akamai_authorities_set" {
  source = "./modules/akamai/d/akamai_authorities_set"

  # contract - (required) is a type of string
  contract = null
}
```

[top](#index)

### Variables

```terraform
variable "contract" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "akamai_authorities_set" "this" {
  contract = var.contract
}
```

[top](#index)

### Outputs

```terraform
output "authorities" {
  description = "returns a list of string"
  value       = data.akamai_authorities_set.this.authorities
}

output "id" {
  description = "returns a string"
  value       = data.akamai_authorities_set.this.id
}

output "this" {
  value = akamai_authorities_set.this
}
```

[top](#index)