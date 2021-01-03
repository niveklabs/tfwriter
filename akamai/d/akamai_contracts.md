# akamai_contracts

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
module "akamai_contracts" {
  source = "./modules/akamai/d/akamai_contracts"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "akamai_contracts" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "contracts" {
  description = "returns a list of object"
  value       = data.akamai_contracts.this.contracts
}

output "id" {
  description = "returns a string"
  value       = data.akamai_contracts.this.id
}

output "this" {
  value = akamai_contracts.this
}
```

[top](#index)