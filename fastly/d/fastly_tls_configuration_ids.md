# fastly_tls_configuration_ids

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
    fastly = ">= 0.28.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fastly_tls_configuration_ids" {
  source = "./modules/fastly/d/fastly_tls_configuration_ids"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "fastly_tls_configuration_ids" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.fastly_tls_configuration_ids.this.id
}

output "ids" {
  description = "returns a set of string"
  value       = data.fastly_tls_configuration_ids.this.ids
}

output "this" {
  value = fastly_tls_configuration_ids.this
}
```

[top](#index)