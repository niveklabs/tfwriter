# fortios_system_replacemsgimage

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_system_replacemsgimage" {
  source = "./modules/fortios/d/fortios_system_replacemsgimage"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "fortios_system_replacemsgimage" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.fortios_system_replacemsgimage.this.id
}

output "image_base64" {
  description = "returns a string"
  value       = data.fortios_system_replacemsgimage.this.image_base64
}

output "image_type" {
  description = "returns a string"
  value       = data.fortios_system_replacemsgimage.this.image_type
}

output "this" {
  value = fortios_system_replacemsgimage.this
}
```

[top](#index)