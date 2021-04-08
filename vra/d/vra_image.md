# vra_image

[back](../vra.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vra = ">= 0.3.5"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vra_image" {
  source = "./modules/vra/d/vra_image"

  # filter - (required) is a type of string
  filter = null
}
```

[top](#index)

### Variables

```terraform
variable "filter" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "vra_image" "this" {
  # filter - (required) is a type of string
  filter = var.filter
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.vra_image.this.description
}

output "external_id" {
  description = "returns a string"
  value       = data.vra_image.this.external_id
}

output "id" {
  description = "returns a string"
  value       = data.vra_image.this.id
}

output "name" {
  description = "returns a string"
  value       = data.vra_image.this.name
}

output "private" {
  description = "returns a bool"
  value       = data.vra_image.this.private
}

output "region" {
  description = "returns a string"
  value       = data.vra_image.this.region
}

output "this" {
  value = vra_image.this
}
```

[top](#index)