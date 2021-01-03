# akamai_property_products

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
module "akamai_property_products" {
  source = "./modules/akamai/d/akamai_property_products"

  # contract_id - (required) is a type of string
  contract_id = null
}
```

[top](#index)

### Variables

```terraform
variable "contract_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "akamai_property_products" "this" {
  contract_id = var.contract_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.akamai_property_products.this.id
}

output "products" {
  description = "returns a list of object"
  value       = data.akamai_property_products.this.products
}

output "this" {
  value = akamai_property_products.this
}
```

[top](#index)