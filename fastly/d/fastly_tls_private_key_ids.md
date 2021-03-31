# fastly_tls_private_key_ids

[back](../fastly.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fastly = ">= 0.27.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fastly_tls_private_key_ids" {
  source = "./modules/fastly/d/fastly_tls_private_key_ids"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "fastly_tls_private_key_ids" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.fastly_tls_private_key_ids.this.id
}

output "ids" {
  description = "returns a set of string"
  value       = data.fastly_tls_private_key_ids.this.ids
}

output "this" {
  value = fastly_tls_private_key_ids.this
}
```

[top](#index)