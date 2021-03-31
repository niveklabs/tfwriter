# akamai_iam_supported_langs

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
module "akamai_iam_supported_langs" {
  source = "./modules/akamai/d/akamai_iam_supported_langs"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "akamai_iam_supported_langs" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.akamai_iam_supported_langs.this.id
}

output "languages" {
  description = "returns a set of string"
  value       = data.akamai_iam_supported_langs.this.languages
}

output "this" {
  value = akamai_iam_supported_langs.this
}
```

[top](#index)