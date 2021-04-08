# vcd_portgroup

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
module "vcd_portgroup" {
  source = "./modules/vcd/d/vcd_portgroup"

  # name - (required) is a type of string
  name = null
  # type - (required) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - Name of NSX-T Tier-0 router."
  type        = string
}

variable "type" {
  description = "(required) - Portgroup type. One of 'NETWORK', 'DV_PORTGROUP'"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "vcd_portgroup" "this" {
  # name - (required) is a type of string
  name = var.name
  # type - (required) is a type of string
  type = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.vcd_portgroup.this.id
}

output "this" {
  value = vcd_portgroup.this
}
```

[top](#index)