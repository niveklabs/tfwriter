# azurestack_platform_image

[back](../azurestack.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azurestack = ">= 0.9.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurestack_platform_image" {
  source = "./modules/azurestack/d/azurestack_platform_image"

  # location - (required) is a type of string
  location = null
  # offer - (required) is a type of string
  offer = null
  # publisher - (required) is a type of string
  publisher = null
  # sku - (required) is a type of string
  sku = null
}
```

[top](#index)

### Variables

```terraform
variable "location" {
  description = "(required)"
  type        = string
}

variable "offer" {
  description = "(required)"
  type        = string
}

variable "publisher" {
  description = "(required)"
  type        = string
}

variable "sku" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "azurestack_platform_image" "this" {
  location  = var.location
  offer     = var.offer
  publisher = var.publisher
  sku       = var.sku
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.azurestack_platform_image.this.id
}

output "version" {
  description = "returns a string"
  value       = data.azurestack_platform_image.this.version
}

output "this" {
  value = azurestack_platform_image.this
}
```

[top](#index)