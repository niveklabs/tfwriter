# akamai_iam_countries

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
module "akamai_iam_countries" {
  source = "./modules/akamai/d/akamai_iam_countries"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "akamai_iam_countries" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "countries" {
  description = "returns a set of string"
  value       = data.akamai_iam_countries.this.countries
}

output "id" {
  description = "returns a string"
  value       = data.akamai_iam_countries.this.id
}

output "this" {
  value = akamai_iam_countries.this
}
```

[top](#index)