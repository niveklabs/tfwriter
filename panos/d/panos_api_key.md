# panos_api_key

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    panos = ">= 1.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_api_key" {
  source = "./modules/panos/d/panos_api_key"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "panos_api_key" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "api_key" {
  description = "returns a string"
  value       = data.panos_api_key.this.api_key
}

output "id" {
  description = "returns a string"
  value       = data.panos_api_key.this.id
}

output "this" {
  value = panos_api_key.this
}
```

[top](#index)