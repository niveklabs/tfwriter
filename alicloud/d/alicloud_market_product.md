# alicloud_market_product

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_market_product" {
  source = "./modules/alicloud/d/alicloud_market_product"

  # available_region - (optional) is a type of string
  available_region = null
  # product_code - (required) is a type of string
  product_code = null
}
```

[top](#index)

### Variables

```terraform
variable "available_region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "product_code" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_market_product" "this" {
  # available_region - (optional) is a type of string
  available_region = var.available_region
  # product_code - (required) is a type of string
  product_code = var.product_code
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_market_product.this.id
}

output "product" {
  description = "returns a list of object"
  value       = data.alicloud_market_product.this.product
}

output "this" {
  value = alicloud_market_product.this
}
```

[top](#index)