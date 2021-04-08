# vcd_resource_schema

[back](../vcd.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vcd = ">= 3.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vcd_resource_schema" {
  source = "./modules/vcd/d/vcd_resource_schema"

  # name - (required) is a type of string
  name = null
  # resource_type - (required) is a type of string
  resource_type = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - Unique name of the structure"
  type        = string
}

variable "resource_type" {
  description = "(required) - Which resource we should list"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "vcd_resource_schema" "this" {
  # name - (required) is a type of string
  name = var.name
  # resource_type - (required) is a type of string
  resource_type = var.resource_type
}
```

[top](#index)

### Outputs

```terraform
output "attributes" {
  description = "returns a set of object"
  value       = data.vcd_resource_schema.this.attributes
}

output "block_attributes" {
  description = "returns a set of object"
  value       = data.vcd_resource_schema.this.block_attributes
}

output "id" {
  description = "returns a string"
  value       = data.vcd_resource_schema.this.id
}

output "this" {
  value = vcd_resource_schema.this
}
```

[top](#index)