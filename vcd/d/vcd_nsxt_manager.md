# vcd_nsxt_manager

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
module "vcd_nsxt_manager" {
  source = "./modules/vcd/d/vcd_nsxt_manager"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - Name of NSX-T manager."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "vcd_nsxt_manager" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.vcd_nsxt_manager.this.id
}

output "this" {
  value = vcd_nsxt_manager.this
}
```

[top](#index)