# alicloud_market_products

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
module "alicloud_market_products" {
  source = "./modules/alicloud/d/alicloud_market_products"

  # category_id - (optional) is a type of string
  category_id = null
  # ids - (optional) is a type of list of string
  ids = []
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # product_type - (optional) is a type of string
  product_type = null
  # search_term - (optional) is a type of string
  search_term = null
  # sort - (optional) is a type of string
  sort = null
  # suggested_price - (optional) is a type of number
  suggested_price = null
  # supplier_id - (optional) is a type of string
  supplier_id = null
  # supplier_name_keyword - (optional) is a type of string
  supplier_name_keyword = null
}
```

[top](#index)

### Variables

```terraform
variable "category_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "name_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "product_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "search_term" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sort" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "suggested_price" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "supplier_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "supplier_name_keyword" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_market_products" "this" {
  category_id           = var.category_id
  ids                   = var.ids
  name_regex            = var.name_regex
  output_file           = var.output_file
  product_type          = var.product_type
  search_term           = var.search_term
  sort                  = var.sort
  suggested_price       = var.suggested_price
  supplier_id           = var.supplier_id
  supplier_name_keyword = var.supplier_name_keyword
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_market_products.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_market_products.this.ids
}

output "products" {
  description = "returns a list of object"
  value       = data.alicloud_market_products.this.products
}

output "this" {
  value = alicloud_market_products.this
}
```

[top](#index)