# bigip_ltm_irule

[back](../bigip.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    bigip = ">= 1.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "bigip_ltm_irule" {
  source = "./modules/bigip/r/bigip_ltm_irule"

  # irule - (required) is a type of string
  irule = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "irule" {
  description = "(required) - The iRule body"
  type        = string
}

variable "name" {
  description = "(required) - Name of the iRule"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "bigip_ltm_irule" "this" {
  irule = var.irule
  name  = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = bigip_ltm_irule.this.id
}

output "this" {
  value = bigip_ltm_irule.this
}
```

[top](#index)