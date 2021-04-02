# aws_pricing_product

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_pricing_product" {
  source = "./modules/aws/d/aws_pricing_product"

  # service_code - (required) is a type of string
  service_code = null

  filters = [{
    field = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "service_code" {
  description = "(required)"
  type        = string
}

variable "filters" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      field = string
      value = string
    }
  ))
}
```

[top](#index)

### Datasource

```terraform
data "aws_pricing_product" "this" {
  service_code = var.service_code

  dynamic "filters" {
    for_each = var.filters
    content {
      field = filters.value["field"]
      value = filters.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.aws_pricing_product.this.id
}

output "result" {
  description = "returns a string"
  value       = data.aws_pricing_product.this.result
}

output "this" {
  value = aws_pricing_product.this
}
```

[top](#index)