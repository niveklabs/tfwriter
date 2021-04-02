# bigip_ltm_irule

[back](../bigip.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    bigip = ">= 1.8.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "bigip_ltm_irule" {
  source = "./modules/bigip/d/bigip_ltm_irule"

  # name - (required) is a type of string
  name = null
  # partition - (required) is a type of string
  partition = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - Name of the irule"
  type        = string
}

variable "partition" {
  description = "(required) - partition of resource group"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "bigip_ltm_irule" "this" {
  name      = var.name
  partition = var.partition
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.bigip_ltm_irule.this.id
}

output "irule" {
  description = "returns a string"
  value       = data.bigip_ltm_irule.this.irule
}

output "this" {
  value = bigip_ltm_irule.this
}
```

[top](#index)