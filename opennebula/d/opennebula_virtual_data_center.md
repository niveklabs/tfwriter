# opennebula_virtual_data_center

[back](../opennebula.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    opennebula = ">= 0.2.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "opennebula_virtual_data_center" {
  source = "./modules/opennebula/d/opennebula_virtual_data_center"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - Name of the VDC"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "opennebula_virtual_data_center" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.opennebula_virtual_data_center.this.id
}

output "this" {
  value = opennebula_virtual_data_center.this
}
```

[top](#index)